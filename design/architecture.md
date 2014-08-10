```
RaceManager

    racers

    timeElapsed

    raceState

        IN_COUNTDOWN  // delegate to the ChristmasTree object to handle
        IN_RACE
        IN_STOP

    events

        COUNTDOWN_STARTED
        FALSE_START
        RACE_STARTED
        ALL_RACERS_FINISHED
        RACER_FINISHED

    startCountdown()  // hand off to ChristmasTree
    startRace()
    killRace()


ChristmasTree

    events

        COUNTDOWN_FINISHED  // hand off back to RaceManager
        FALSE_START_OCCURED

    watchForFalseStarts()  // Add FalseStartMonitor as observer


Track

    slots
        e.g. [racer1Obj, racer2Obj, racer3Obj, racer4Obj]
    dist

    assignSlotToRacer(slotNumber, racerObj)
    connectSensor()


Racer

    participant
    color
    currentDist()  // return numTicksOccurredUntil(now) * RaceSystem.rollerCircumf


FalseStartMonitor

    racersFalseStartSecs
        e.g. {"racer1UUID": null, "racer2": 0.001, racer3


Sensor

    numTicksOccurredUntil(elapsedTimeSecs)


RaceSystem

    rollerCircumf


//
// Schema models
//

Tournament
    races
    startDatetime


Participant
    name
    gender
    bestTimeSecs


Race
    participants
    results

```
