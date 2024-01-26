---
layout: essay
type: essay
title: "How Do I Ask a Smart Question?"
# All dates must be YYYY-MM-DD format!
date: 2024-01-25
published: true
labels:
  - Discussion
---

<img width="500px" class="rounded float-start pe-4" src=".img/question-clipart-transparent-23.png">

## My Experience Asking Questions

As someone who grew up assembling PCs and modding video games on my computer, I know exactly what it's like to encounter smart and "not smart" questions. I've personally spent a few hundred hours on Reddit just for troubleshooting advice because I know I'm talking to real people who know exactly what I'm talking about. There's a reason why searching for a technical question is typically followed by "Reddit" or "StackOverflow" because you're more likely to get real, tried-and-true solutions rather than coming across the tenth article telling you to "turn it off/on" again.

## What's a "Good" Question?

Speaking of StackOverflow, it is a deep well of information for software engineers at all skill levels. Whether you're a senior developer or a student who just printed "Hello World" for the first time, everyone will eventually find themselves scrolling through StackOverflow for a solution to their problem. However, if you want to find valuable information, you need to ask valuable questions, or at least find them. It is straightforward to ask, "I did x to achieve y, but I'm getting z instead. Please fix!!!" and assume other developers will know exactly what you're talking about and fix your problem for you. While I'm sure there are a few developers exactly like that, most people will not even bother with said question if it sounds like the original poster just wants to be spoon-fed the answers. There needs to be some effort by the poster to show other developers that they are willing to learn the material. This also makes it much easier for people to answer your question if they are on the same page as you. Take this question, for example:

```
Q: How do I avoid checking for nulls in Java?

I use x != null to avoid NullPointerException. Is there an alternative?

if (x != null) {
    // ...
}

```

This is one of StackOverflow's top-voted questions for Java, indicating that this might be a good question. While it is really short and something that could be Googled, it is still a high-quality, valid question rather than a simple "please fix" type of question. It demonstrates that the original poster knows exactly what they want to achieve, how they achieve that, and is simply asking other users for recommendations on improving their code. They have shown that they put effort in first before asking their question and managed to elicit many useful answers. In fact, the top answer provides a very clear and detailed answer with the commenter giving methods such as the  ```Objects.requireNonNull(foo)``` method for Java 1.7 or above or ```assertions``` for earlier Java versions.

## Please Fix my Bad Code!

On the other hand, while there are plenty of "good" questions on StackOverflow, there is an entire sea of "bad" questions as well. Knowing the difference between the two can save a lot of headache and mindless scrolling to find the right information. Take this example:

```
Q: java.lang.NullPointerException error help me [closed]

it's my logCat.

04-09 09:11:18.178: E/AndroidRuntime(829): FATAL EXCEPTION: main
04-09 09:11:18.178: E/AndroidRuntime(829): java.lang.NullPointerException
04-09 09:11:18.178: E/AndroidRuntime(829):  at com.example.androidresim.Activitygiris.onLoadScene(Activitygiris.java:84)
04-09 09:11:18.178: E/AndroidRuntime(829):  at org.anddev.andengine.ui.activity.BaseGameActivity.doResume(BaseGameActivity.java:158)
04-09 09:11:18.178: E/AndroidRuntime(829):  at org.anddev.andengine.ui.activity.BaseGameActivity.onWindowFocusChanged(BaseGameActivity.java:82)
04-09 09:11:18.178: E/AndroidRuntime(829):  at com.android.internal.policy.impl.PhoneWindow$DecorView.onWindowFocusChanged(PhoneWindow.java:2462)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.view.View.dispatchWindowFocusChanged(View.java:7578)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.view.ViewGroup.dispatchWindowFocusChanged(ViewGroup.java:962)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.view.ViewRootImpl$ViewRootHandler.handleMessage(ViewRootImpl.java:3115)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.os.Handler.dispatchMessage(Handler.java:99)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.os.Looper.loop(Looper.java:137)
04-09 09:11:18.178: E/AndroidRuntime(829):  at android.app.ActivityThread.main(ActivityThread.java:5103)
04-09 09:11:18.178: E/AndroidRuntime(829):  at java.lang.reflect.Method.invokeNative(Native Method)
04-09 09:11:18.178: E/AndroidRuntime(829):  at java.lang.reflect.Method.invoke(Method.java:525)
04-09 09:11:18.178: E/AndroidRuntime(829):  at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:737)
04-09 09:11:18.178: E/AndroidRuntime(829):  at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:553)
04-09 09:11:18.178: E/AndroidRuntime(829):  at dalvik.system.NativeStart.main(Native Method)

and it's my class.

public class Activitygiris extends BaseGameActivity {

    private static final int CAMERA_WIDTH=800;
    private static final int CAMERA_HEIGHT=480;


    private Camera camera;
    private Engine engine;
    Scene sahne;

    private Texture texSaha,texOyuncu1,texOyuncu2,texRedWins,texBlueWins;
    private TextureRegion texRegSaha,texRegOyuncu1,texRegOyuncu2,texRegRedWins,texRegBlueWins;
    private Sprite spriteSaha,spriteOyuncu1,spriteOyuncu2,spriteRedWins,spriteBlueWins;

    private TimerHandler timerBeklet;


    @Override
    public Engine onLoadEngine() {
        // TODO Auto-generated method stub

        camera= new Camera(0,0,CAMERA_WIDTH,CAMERA_HEIGHT);
        final EngineOptions engineoptions = new EngineOptions(true,ScreenOrientation.LANDSCAPE,new FillResolutionPolicy(),camera);
        engineoptions.getTouchOptions().setRunOnUpdateThread(true);
        engine = new Engine(engineoptions);



        return engine;
    }

    @Override
    public void onLoadResources() {
        // TODO Auto-generated method stub
    texSaha=new Texture(1024,512,TextureOptions.BILINEAR_PREMULTIPLYALPHA);
    texOyuncu1 = new Texture(128,128,TextureOptions.BILINEAR_PREMULTIPLYALPHA);
    texOyuncu2 = new Texture(128,128,TextureOptions.BILINEAR_PREMULTIPLYALPHA);
    texRedWins = new Texture(64,256,TextureOptions.BILINEAR_PREMULTIPLYALPHA);  
    texBlueWins = new Texture(64,256,TextureOptions.BILINEAR_PREMULTIPLYALPHA);

    texRegSaha = TextureRegionFactory.createFromAsset(texSaha, this, "gfx/Arkaplan.jpg",0,0);
    texRegOyuncu1 = TextureRegionFactory.createFromAsset(texOyuncu1, this, "gfx/kol1.png",0,0);
    texRegOyuncu2 = TextureRegionFactory.createFromAsset(texOyuncu2, this, "gfx/kol2.png",0,0); 
    texRegBlueWins = TextureRegionFactory.createFromAsset(texBlueWins, this, "gfx/bluewins.png",0,0);
    texRegRedWins = TextureRegionFactory.createFromAsset(texRedWins, this, "gfx/redwins.png",0,0);

    Texture [] textures = {texSaha,texOyuncu1,texOyuncu2,texBlueWins,texRedWins };  

    mEngine.getTextureManager().loadTextures(textures);
    }
    @Override
    public Scene onLoadScene() {
        // TODO Auto-generated method stub

        this.engine.registerUpdateHandler(new FPSLogger());
        this.sahne=new Scene();

        spriteSaha = new Sprite(0, 0, texRegSaha);
        spriteOyuncu1 = new Sprite(600, CAMERA_HEIGHT/2-64, texRegOyuncu1);
        spriteOyuncu2 = new Sprite(50, CAMERA_HEIGHT/2-64, texRegOyuncu2);
        spriteRedWins = new Sprite(CAMERA_HEIGHT-128,CAMERA_HEIGHT/2-128,texRegRedWins);
        spriteRedWins = new Sprite(CAMERA_HEIGHT+32,CAMERA_HEIGHT/2-128,texRegBlueWins.clone());

        spriteBlueWins.setVisible(false);

        mEngine.registerUpdateHandler(timerBeklet = new TimerHandler(3, false,new ITimerCallback() {

            @Override
            public void onTimePassed(TimerHandler pTimerHandler) {
                // TODO Auto-generated method stub


                spriteRedWins.setRotation(180);
                mEngine.registerUpdateHandler(timerBeklet= new TimerHandler(3,false, new ITimerCallback() {

                    @Override
                    public void onTimePassed(TimerHandler pTimerHandler) {
                        // TODO Auto-generated method stub

                        spriteBlueWins.setVisible(true);
                        spriteRedWins.setVisible(false);

                    }
                }));

            }
        }));

        this.sahne.attachChild(spriteSaha);
        this.sahne.attachChild(spriteOyuncu1);
        this.sahne.attachChild(spriteOyuncu2);
        this.sahne.attachChild(spriteBlueWins);
        this.sahne.attachChild(spriteRedWins);


        return this.sahne;  
    }

    @Override
    public void onLoadComplete() {
        // TODO Auto-generated method stub

    }

}

Help me, please..

```

The original poster simply posted a log and their source code with no additional background information. What exactly is the problem? What are they trying to achieve? It certainly doesn't seem like they tried to help themselves first. It's no surprise that this question was closed and received four downvotes. You simply can't expect people to take your code and debug it for free. The original poster doesn't seem like they've also narrowed down exactly what their problem is. They did put the specific error being thrown; however, they do not point out exactly where in the code that error is being thrown. Luckily for the original poster, a commenter pointed out that the exception was being thrown due to the fact that ```spriteBlueWin``` was referencing ```null```, however unlike the previous question, this is the only answer and we're not sure if the code still achieved the desired result.

## Final Remarks
To recap, a smart question will be given smart answers. Attempt to do your troubleshooting and research first. Be specific about what you're trying to do and what's going wrong. Great questions with great answers will very likely help other people who have a similar issue down the road.

Note: ChatGPT was used to fix any spelling/grammatical errors.
