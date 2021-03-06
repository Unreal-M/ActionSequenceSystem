[![license](http://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/karsion/ActionSequenceSystem/master/LICENSE.TXT)
[![release](https://img.shields.io/badge/release-v1.0.1-blue.svg)](https://github.com/karsion/ActionSequenceSystem/master/releases)

# ActionSequenceSystem
A multifunctional timer system for  Unity3D.

``` csharp
//Start a once timer
this.Delayer(1, () => Debug.Log(1));
this.Sequence().Interval(1).Action(() => Debug.Log(1));//Same

//Allso use transform as a ID to start a sequence
transform.Delayer(1, () => Debug.Log(1));

//Start a loop timer
this.Looper(0.5f, 3, false, () => Debug.Log(-1));
this.Sequence().Loop(3).Interval(0.5f).Action(() => Debug.Log(-1));//Same

//Start a custom sequence
this.Sequence()
    .Interval(2)
    .Action(() => Debug.Log("Test1"))
    .Interval(3)
    .Action(() => Debug.Log("Test2"))
    .Interval(1)
    .Action(() => Debug.Log("Test3 end"));

//Check Q key per 0.2 seconds
this.Sequence()
    .Loop()
    .Interval(0.2f)
    .Condition(() => Input.GetKeyDown(KeyCode.Q))
    .Action(n => Debug.Log("Q键 按下次数" + n));

//Stop all sequences start by this ID
this.StopSequence();

//Allso transform as ID
transform.StopSequence();
```
