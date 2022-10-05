`class` -> VoteRecoder
    `static String`  -> nameCandidatePresident1
    `static String`  -> nameCandidatePresident2
    `static String`  -> nameCandidateVicePresident1
    `static String`  -> nameCandidateVicePresident2
    `static int` -> votesCandidatePresident1
    `static int` -> votesCandidatePresident2
    `static int` -> votesCandidateVicePresident1
    `static int` -> votesCandidateVicePresident2
    `int` -> myVoteForPresident (0 for none, 1 for President1, 2 for President 2)
    `int` -> myVoteForVicePresident (0 for none, 1 for VicePresident1, 2 for Vice 
                                                            President 2)

## Methods:
`static void` -> setCandidatesPresident(String name1, String name2)
`static void` -> setCandidatesVicePresident(String name1, String 
                                                                                          name2)
`static void` -> resetVotes (vote count to zero)
`static String` getCurrentVotePresident(returns votes of both Presidents)
`static String` getCurrentVoteVicePresident(returns votes of both 
                                                                             VicePresidents)
`public void` getAndConfirmVotes (get, confirm and records the votes of an 
                                                            individual)

`private String` confirmVotes (displays votes for both President and Vice 
President and ask them wethter they are happy or not Happy = `true` Not Happy= `false`)
`private String` getVotes(return the vote of an individual for president and vice 
                                             President)
`private void` recordVotes (increments into static variables)

```
Create a program that will conduct an election. The candidates for president are Imran and Nawaz. The candidates for vice president are Khan and Sharif. Use a loop to record the votes of many voters. Create a new VoteRecorder object for each voter. After all the voters are done, present the results.
```

**Note**:  The usage of enum is MUST in the above class.
