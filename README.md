# Hello-Word

package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.Servo;
import com.qualcomm.robotcore.hardware.DcMotor;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;



@TeleOp(name = "Following Tutorial")
public class FirstTimeCodingRobot extends LinearOpMode 
{
    
    private DcMotor leftBackMotor;
    private DcMotor rightBackMotor;
    private DcMotor leftFrontMotor;
    private DcMotor rightFrontMotor;
@Override
    public void runOpMode() throws InterruptedException
    {
    rightBackMotor = hardwareMap.dcMotor.get("rightBackMotor");
    rightFrontMotor = hardwareMap.dcMotor.get("rightFrontMotor");
    leftFrontMotor = hardwareMap.dcMotor.get("leftFrontMotor");
    leftBackMotor = hardwareMap.dcMotor.get("leftBackMotor");
    
    
    leftFrontMotor.setDirection(DcMotor.Direction.REVERSE);
    leftBackMotor.setDirection(DcMotor.Direction.REVERSE);
    
    waitForStart();
    
     while(opModeIsActive())
    {
        rightBackMotor.setPower(-gamepad1.left_stick_y - gamepad1.left_stick_x + gamepad1.right_stick_x);
        rightFrontMotor.setPower(-gamepad1.left_stick_y + gamepad1.left_stick_x + gamepad1.right_stick_x);
        leftBackMotor.setPower(-gamepad1.left_stick_y + gamepad1.left_stick_x - gamepad1.right_stick_x);
        leftFrontMotor.setPower(-gamepad1.left_stick_y - gamepad1.left_stick_x - gamepad1.right_stick_x);
        
    }
    }
}
