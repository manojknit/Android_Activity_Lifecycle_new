# Android Activity Lifecycle
####                                                                                                     By Manoj Kumar
## Introduction 
Android Activity Lifecycle is descrived in following diagram. This project helps in understanding these events.
<img src="images/Android app life cycle.png">


## How to Run
1.	Prerequisite: Android Studio, some Java knowledge
2.	Download or clone project code and open in Android studio.
3.	Run in Nexus 5X API 26 emulator.


## Technologies Used
1.	Java.
2.	Android Studio


## Application Screenshots
#### Main Screen with event logs
<img src="images/Android Emulator - Nexus_5X_API_265554 2018-02-18 17-46-31.png">


```
   public class ActivityA extends Activity {

    private String mActivityName;
    private TextView mStatusView;
    private TextView mStatusAllView;
    private StatusTracker mStatusTracker = StatusTracker.getInstance();

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_a);
        mActivityName = getString(R.string.activity_a);
        mStatusView = (TextView)findViewById(R.id.status_view_a);
        mStatusAllView = (TextView)findViewById(R.id.status_view_all_a);
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_create));
        Utils.printStatus(mStatusView, mStatusAllView);
    }

    @Override
    protected void onStart() {
        super.onStart();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_start));
        Utils.printStatus(mStatusView, mStatusAllView);
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_restart));
        Utils.printStatus(mStatusView, mStatusAllView);
    }

    @Override
    protected void onResume() {
        super.onResume();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_resume));
        Utils.printStatus(mStatusView, mStatusAllView);
    }

    @Override
    protected void onPause() {
        super.onPause();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_pause));
        Utils.printStatus(mStatusView, mStatusAllView);
    }

    @Override
    protected void onStop() {
        super.onStop();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_stop));
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        mStatusTracker.setStatus(mActivityName, getString(R.string.on_destroy));
        mStatusTracker.clear();
    }

    public void startDialog(View v) {
        Intent intent = new Intent(ActivityA.this, DialogActivity.class);
        startActivity(intent);
    }

    public void startActivityB(View v) {
        Intent intent = new Intent(ActivityA.this, ActivityB.class);
        startActivity(intent);
    }

    public void startActivityC(View v) {
        Intent intent = new Intent(ActivityA.this, ActivityC.class);
        startActivity(intent);
    }

    public void finishActivityA(View v) {
        ActivityA.this.finish();
    }
}
```

#### Dialog Popup.
<img src="images/Android Emulator - Nexus_5X_API_265554 2018-02-18 17-47-15.png">


## Refrence
- [*Android Activity Lifecycle*](https://www.javatpoint.com/android-life-cycle-of-activity) 
- SJSU.edu

## Thank You
#### [*Manoj Kumar*](https://www.linkedin.com/in/manojkumar19/)
#### Solutions Architect
