How to build flexidag :

For example : YoloV4 model

Step 0 : before start , prepare .onnx model
	put onnx model at below directory : 
	$ cd /home/csi/projects/bub_cv25_adk2.3.0/rtos/refapp/cnn_testbed/cv/public_nn/cnn_model/yolov4
	 
Step 1 :  At bub_cv25_adk2.3.0
	Go to path:
	$ cd /home/csi/projects/bub_cv25_adk2.3.0/rtos/refapp/cnn_testbed/cv/public_nn/diag/picinfo/yolov4
	
Step 2 : At path: bub_cv25_adk2.3.0/rtos/refapp/cnn_testbed/cv/public_nn/diag/picinfo/yolov4

	$ vi Makefile.in
	
	and do parameter settings
	
Step 3 : Create a directory for building fleidag 
	go to dir :
	command:
	$ cd /home/csi/projects/bub_cv25_adk2.3.0/flexidags (Alister put all flexidags folder)
	$ mkdir flexidag_yolov4_384_7cls
	$ source rtos/build/maintenance/env/env_set.sh
	$ source rtos/refapp/svc/env/refapp-svc-env
	$ remoteconfig ${RTOS}/refapp/cnn_testbed/cv/public_nn/diags/picinfo/yolov4 (your full path of target diag)
	$ vi Makefile  (Start setting parameter)
	$ make
	
	make command will build flexidag and genertae "flexibin.bin" file
	
Step 4 : Copy flexibin.bin file to app/app_yolov4_seg_resnet18/flexibin

	$ cd out/yolov4_384_7cls_pr90__bub_run_dir/flexibin/flexibin.bin /home/csi/projects/argos_2.3.0/ambalink_sdk_4_14/pkg/ambacv/arm_framework/app/app_yolov4_seg-resnet18/flexibin/flexibin_yolov4.bin
	

Step 5 : Build app_yolov4_seg_resnet18

 $ cd /home/csi/projects/argos_2.3.0/ambalink_sdk_4_14/output.oem/ambalink/diags/
 $ rm -rf app_yolov4_seg_resnet18
 $ make app_yolov4_seg_resnet18-init
 $ make app_yolov4_seg_resnet18-build
      
Step 6: 

