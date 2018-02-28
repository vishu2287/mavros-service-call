# mavros-service-call
mavros-service-call


rosservice call /mavros/set_stream_rate 0 10 1
or if you are using C++:

ros::NodeHandle n;


ros::ServiceClient client = n.serviceClient<mavros::StreamRate>("/mavros/set_stream_rate");

mavros::StreamRate srv;

srv.request.stream_id = 0;

srv.request.message_rate = 10;

srv.request.on_off = 1;


if(client.call(srv)){


    ROS_INFO("Service called");
    }else{
    ROS_INFO("Failed to call service");
    }
