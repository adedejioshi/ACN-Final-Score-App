# ACN-Final-Score-App (java file)

package com.example.android.acnfinalscoreapp;

import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    private TextView CamScore;
    private TextView EgyptScore;
    private TextView PossCam;
    private TextView PossEgypt;
    private TextView OffCam;
    private TextView OffEgypt;
    private TextView YellowCam;
    private TextView YellowEgypt;
    private TextView RedCam;
    private TextView RedEgypt;
    private TextView FoulCam;
    private TextView FoulEgypt;
    private TextView AttemptCam;
    private TextView AttemptEgypt;

    public int cameroun= 0;
    public int egypt= 0;
    public int poss1= 0;
    public int poss2= 0;
    public int TotPoss= 100;
    public int offside1= 0;
    public int offside2= 0;
    public int yellow1= 0;
    public int yellow2= 0;
    public int red1= 0;
    public int red2= 0;
    public int foul1= 0;
    public int foul2= 0;
    public int attempt1= 0;
    public int attempt2= 0;

    private Button CamPoss;
    private Button Cameroun;
    private Button Egypt;
    private Button EgyptPoss;
    private Button CamOffside;
    private Button EgyptOffside;
    private Button CamYellow;
    private Button EgyptYellow;
    private Button CamRed;
    private Button EgyptRed;
    private Button CamFoul;
    private Button EgyptFoul;
    private Button CamAttempt;
    private Button EgyptAttempt;
    private Button reset;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        CamScore = (TextView)findViewById(R.id.cameroun_score_view);
        EgyptScore = (TextView)findViewById(R.id.egypt_score_view);
        Cameroun = (Button)findViewById(R.id.goal1);
        Egypt = (Button)findViewById(R.id.goal2);

        PossCam = (TextView)findViewById(R.id.cam_poss);
        PossEgypt = (TextView)findViewById(R.id.egypt_poss);
        CamPoss = (Button)findViewById(R.id.possession1);
        EgyptPoss = (Button)findViewById(R.id.possession2);

        OffCam = (TextView)findViewById(R.id.cam_offside);
        OffEgypt = (TextView)findViewById(R.id.egypt_offside);
        CamOffside = (Button)findViewById(R.id.offside1);
        EgyptOffside = (Button)findViewById(R.id.offside2);

        YellowCam = (TextView)findViewById(R.id.cam_yellow);
        YellowEgypt = (TextView)findViewById(R.id.egypt_yellow);
        CamYellow = (Button)findViewById(R.id.yellow1);
        EgyptYellow = (Button)findViewById(R.id.yellow2);

        RedCam = (TextView)findViewById(R.id.cam_red);
        RedEgypt = (TextView)findViewById(R.id.egypt_red);
        CamRed = (Button)findViewById(R.id.red1);
        EgyptRed = (Button)findViewById(R.id.red2);

        FoulCam = (TextView)findViewById(R.id.cam_foul);
        FoulEgypt = (TextView)findViewById(R.id.egypt_foul);
        CamFoul = (Button)findViewById(R.id.foul1);
        EgyptFoul = (Button)findViewById(R.id.foul2);

        AttemptCam = (TextView)findViewById(R.id.cam_attempt);
        AttemptEgypt = (TextView)findViewById(R.id.egypt_attempt);
        CamAttempt = (Button)findViewById(R.id.attempt1);
        EgyptAttempt = (Button)findViewById(R.id.attempt2);
        reset = (Button)findViewById(R.id.reset);

        /**(Cameroun)Score
         * This method is called when the GOAL BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the GOAL SCORE TEXTVIEW.
         */
        Cameroun.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                cameroun = cameroun+1;
                CamScore.setText(cameroun +"");
            }
    });
        /**(Egypt)Score
         * This method is called when the GOAL BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the GOAL SCORE TEXTVIEW.
         */
        Egypt.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                egypt = egypt+1;
                EgyptScore.setText(egypt +"");
            }
        });
        /**(Cameroun)Possession
         * * This method is called when the POSSESSION BUTTON for Cameroun is clicked.
         * Here, for every click, FIVE PERCENT additional point is added to the Cameroun POSSESSION TEXTVIEW.
         * Moreso, Egypt's possession would be changed as well since it is a function of percentage.
         */
        CamPoss.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                poss1 = poss1+5;
                PossCam.setText(poss1 + "%");
                PossEgypt.setText((poss2 = TotPoss-poss1) + "%");
            }
        });
        /**(Egypt)Possession
         * This method is called when the POSSESSION BUTTON for Egypt is clicked.
         * Here, for every click, FIVE PERCENT additional point is added to the Egypt POSSESSION TEXTVIEW.
         * Moreso, Cameroun's possession would be changed as well since it is a function of percentage.
         */
        EgyptPoss.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                poss2 = poss2+5;
                PossEgypt.setText(poss2 + "%");
                PossCam.setText((poss1 = TotPoss-poss2) + "%");
            }
        });
        /**(Cameroun)Offside
         * This method is called when the OFFSIDE BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the OFFSIDE TEXTVIEW.
         */
        CamOffside.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                offside1 = offside1+1;
                OffCam.setText(offside1 +"");
            }
        });
        /**(Egypt)Offside
         * This method is called when the OFFSIDE BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the OFFSIDE CARD TEXTVIEW.
         */
        EgyptOffside.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                offside2 = offside2+1;
                OffEgypt.setText(offside2 +"");
            }
        });
        /**(Cameroun)Yellow Card
         * This method is called when the YELLOW CARD BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the YELLOW CARD TEXTVIEW.
         */
        CamYellow.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                yellow1 = yellow1+1;
                YellowCam.setText(yellow1 +"");
            }
        });
        /**(Egypt)Yellow Card
         * This method is called when the YELLOW CARD BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the YELLOW CARD TEXTVIEW.
         */
        EgyptYellow.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                yellow2 = yellow2+1;
                YellowEgypt.setText(yellow2 +"");
            }
        });
        /**(Cameroun)Red Card
         * This method is called when the RED CARD BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the RED CARD TEXTVIEW.
         */
        CamRed.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                red1 = red1+1;
                RedCam.setText(red1 +"");
            }
        });
        /**(Egypt)Red Card
         * This method is called when the RED CARD BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the RED CARD TEXTVIEW.
         */
        EgyptRed.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                red2 = red2+1;
                RedEgypt.setText(red2 +"");
            }
        });
        /**(Cameroun)Foul
         * This method is called when the FOUL BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the FOUL TEXTVIEW.
         */
        CamFoul.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                foul1 = foul1+1;
                FoulCam.setText(foul1 +"");
            }
        });
        /**(Egypt)Foul
         * * This method is called when the FOUL BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the FOUL TEXTVIEW.
         */
        EgyptFoul.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                foul2 = foul2+1;
                FoulEgypt.setText(foul2 +"");
            }
        });
        /**(Cameroun) Attempt
         * * This method is called when the GOAL ATTEMPT BUTTON for Cameroun is clicked.
         * Here, for every click, one additional point is added to the GOAL ATTEMPT TEXTVIEW.
         */
        CamAttempt.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                attempt1 = attempt1+1;
                AttemptCam.setText(attempt1 +"");
            }
        });
        /**(Egypt)Attempt
         * This method is called when the GOAL ATTEMPT BUTTON for Egypt is clicked.
         * Here, for every click, one additional point is added to the GOAL ATTEMPT TEXTVIEW.
         */
        EgyptAttempt.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick (View view){
                attempt2 = attempt2+1;
                AttemptEgypt.setText(attempt2 +"");
            }
        });
        /**
         * This method is called when the RESET BUTTON is clicked.
         * Here, all the parameters is set to zero.
         */
        reset.setOnClickListener(new View.OnClickListener(){
            @Override
                    public void onClick (View v){
                cameroun= 0;
                CamScore.setText(cameroun +"");
                egypt= 0;
                EgyptScore.setText(egypt +"");
                poss1= 0;
                PossCam.setText(poss1 + "%");
                poss2= 0;
                PossEgypt.setText(poss2 + "%");
                offside1= 0;
                OffCam.setText(offside1 +"");
                offside2= 0;
                OffEgypt.setText(offside2 +"");
                yellow1= 0;
                YellowCam.setText(yellow1 +"");
                yellow2= 0;
                YellowEgypt.setText(yellow2 +"");
                red1= 0;
                RedCam.setText(red1 +"");
                red2= 0;
                RedEgypt.setText(red2 +"");
                foul1= 0;
                FoulCam.setText(foul1 +"");
                foul2= 0;
                FoulEgypt.setText(foul2 +"");
                attempt1= 0;
                AttemptCam.setText(attempt1 +"");
                attempt2= 0;
                AttemptEgypt.setText(attempt2 +"");
            }
        });
}
}
