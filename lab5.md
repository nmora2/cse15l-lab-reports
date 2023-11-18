PART 1:
Failed test:

``` java
  @Test
  public void reverse() {
    int[] input1 = {0, 1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1, 0}, input1);
  }
```
Output:

![Image](failedOutput.png)


Does not induce a failure:
``` java
 @Test 
  public void testEmpty() {
  int[] input = {};
  assertArrayEquals(new int[]{}, ArrayExamples.reversed(input));
  }
```

Output: 
![Image](passedFailCode.png)

The bug before:
``` java
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
The bug after:
``` java
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```


Explanation: 
- The fix addresses the issue because at first, the method returnes the original array
instead of the new Array. If we wanted the array to be reversed, we would have to return
the new array and not the original which is why the code I provided, after the bug, works
for reversing the array. 

PART 2:
- Example 1:
``` java
grep -w "treatment" */1468-6708-3-10.txt
```

Output:
``` java
older, between those randomized to treatment initiated with
        a diuretic (chlorthalidone) and treatment initiated with
        recommendation to discontinue the doxazosin treatment arm
        compare these features between the two treatment
          distributed across the four treatment groups, reported as
          differences among treatment groups.
          treatment groups were presented for baseline
          characteristics of the treatment and HF outcome groups
          chlorthalidone treatment groups, stratified for HF
          pre-trial antihypertensive treatment durations. None of
          Table 2presents post-event pharmacologic treatment of
          participants with HF and antihypertensive treatment of
          treatment groups, a diuretic, ACE-inhibitor or
          P = 0.83) between the two treatment
          treatment group who had been previously hospitalized for
          significantly differ in the two treatment groups (RR
        documentation were similar in the two treatment groups [ 2
        treatment groups confirmed the consistency of HF event
        the two treatment groups.
        chlorthalidone treatment groups showed a rather high 20%
        and chlorthalidone treatment groups represented a desirable
```

- Example 2:

``` java
grep -w "September" */1468-6708-3-10.txt
```

  Output:
  ``` java
  Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
    They were planning to hijack these planes and turn them into large guided missiles, loaded with up to 11,400 gallons of jet fuel. By 8:00 A.M. on the morning of Tuesday, September 11,2001, they had defeated all the security layers that America's civil aviation security system then had in place to prevent a hijacking. The Hijacking of American 11 American Airlines Flight 11 provided nonstop service from Boston to Los Angeles. On September 11, Captain John Ogonowski and First Officer Thomas McGuinness piloted the Boeing 767. It carried its full capacity of nine flight attendants. Eighty-one passengers boarded the flight with them (including the five terrorists).22 The plane took off at 7:59. Just before 8:14, it had climbed to 26,000 feet, not quite its initial assigned cruising altitude of 29,000 feet. All communications and flight profile data were normal. About this time the "Fasten Seatbelt" sign would usually have been turned off and the flight attendants would have begun preparing for cabin service.
    The Hijacking of American 77 American Airlines Flight 77 was scheduled to depart from Washington Dulles for Los Angeles at 8:10. The aircraft was a Boeing 757 piloted by Captain Charles F. Burlingame and First Officer David Charlebois. There were four flight attendants. On September 11, the flight carried 58 passengers.
    FAA Mission and Structure. As of September 11, 2001, the FAA was mandated by law to regulate the safety and security of civil aviation. From an air traffic controller's perspective, that meant maintaining a safe distance between airborne aircraft.
    On the morning of September 11, Secretary Rumsfeld was having breakfast at the Pentagon with a group of members of Congress. He then returned to his office for his daily intelligence briefing. The Secretary was informed of the second strike in New York during the briefing; he resumed the briefing while awaiting more information. After the Pentagon was struck, Secretary Rumsfeld went to the parking lot to assist with rescue efforts.
    There is no evidence that NORAD headquarters or military officials in the NMCC knew-during the morning of September 11-that the Andrews planes were airborne and operating under different rules of engagement.
    The details of what happened on the morning of September 11 are complex, but they play out a simple theme. NORAD and the FAA were unprepared for the type of attacks launched against the United States on September 11, 2001. They struggled, under difficult circumstances, to improvise a homeland defense against an unprecedented challenge they had never before encountered and had never trained to meet.
```

  Explanation:
  This command, grep-w "__" */file ,finds the word "treatment" and "September" in the file that I want to look at and it returns every line that includes those words, but this command only works for COMPLETE words.




- Example 3:
  
``` java
grep -c "September" */chapter-1.txt
```

Output: 
``` java
      7
```

- Example 4:
  
``` java
grep -c "goat" */1471-213X-1-12.txt
```

Output: 
``` java
     1
```

Explanation:
This command, grep-c "__" */file ,counts the amount of times the word occurs in the
file that I want it to look at. 



- Example 5
``` java
grep -b --colour -n "environmental" */journal.pbio.0020019.txt
```
Output:
``` java
7:118:        given the amount of environmental variation they encounter during development and the
10:399:        environmental variation (Waddington 1942). Clearly, such a mechanism would have important
16:987:        genetic or environmental circumstances, then the stored genetic variation will be released,
31:2145:        (4) this function may be compromised by environmental factors, e.g., heat shock.
38:2576:        stabilisation and environmental coupling such as those provided by Hsp90 (Siegal and
58:4518:        changed from on to off or vice versa (i.e., there was a shift in the environmental
65:5190:        be linked to an environmental change in order to be beneficial.
68:5451:        response to environmental or genetic change, are not unique to Hsp90. Indeed, the
71:5733:        by an environmental change, but can be produced by a gene ‘knockout’. These results may go
128:10299:        genetic and environmental variation. The stabilisation of neural activity may have
```


- Example 6:
  
``` java
 grep -b --colour -n "treated" */journal.pbio.0020019.txt
```

Output:
``` java
28:1854:        abnormalities; (2) individuals treated with a pharmacological inhibitor of Hsp90 show
```
Explanation:
This command, grep -b --colour -n "__" */file ,highlights the word that I
want to find in the file. 




- Example 7:
  
``` java
technical % grep "Highly" */chapter-5.txt
```

Output:
``` java
Highly educated and equally comfortable in a government office or a terrorist
```

- Example 8:
  
``` java
technical % grep "G2" */1471-213X-1-12.txt
```

Output:
``` java
or G2 phase into the preactivated recipients after reducing
          S phase and 6.4 ± 0.1% were at the G2/M phase. In the
          the S phase and 54.1 ± 4.4% were at the G2/M phase.
          to induce G2/M phase arrest. After gentle pipetting,
          at the G2/M phase as described by Wakayama et al. [ 13].
            100 μl of G2.2 medium [ 60] and continued to be
```

Explanation:
This command, grep "__" */file ,looks for the exact pattern that I input. This command
works for a letter and also works for COMPLETE words. 



SOURCE: I typed "man grep" into the terminal, and it gave me so many options of how
I can use the command "grep" for technical. 







