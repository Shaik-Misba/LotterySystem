**Participant.java**
<p><code> <b>@Entity
          @Table(name="participant")</b>
          public class Participant {
             <b> @Id
              @GeneratedValue(strategy = GenerationType.IDENTITY)
              private Integer participantId; </b>
          }
  
</code></p>

**ParticipantDTO.java**
<p><code>
        @NotNull(message="{lottery.name.absent}")
        @Pattern(regexp="[A-Za-z]+(\\s[A-Za-z]+)*",message="{lottery.name.invalid
</code></p>
private Integer participentId; NotNull(message(lottery.name.absent)")

Pattern(regexp="[A-Za-z]+(\\s[A-Za-z]+)*"message"(lottery.name.invalid}")

private String name; NotNull(message = "(lottery.age.absent)")

NotNull(message(lottery.mailid.absent)") @Pattern(regexp = "([a-z0-9]+)[@](infy gmail yahoo)(.com)",message "lottery.mailid.invalid)") private String mailld;

NotNull(message (lottery.contactno.absent)")

private Long contactio;

@NotNull(message = "(lottery.couponnumber.absent)") @Pattern(regexp = "[A-Z](3) [0-9](3)", message = "(lottery.couponnumber.invalid)")

private String couponfNumber; @NotNull(message"(lottery.winningamount.absent}")

12

13

14

15

private Integer age;

16

17

18

19

20

21

22

23

24-

25

26

27

28

29 30

31

324

34 354

36

37

BE

39 40

private Integer winningAmount; public Integer getParticipantIdprivate Integer participentId; NotNull(message(lottery.name.absent)")

Pattern(regexp="[A-Za-z]+(\\s[A-Za-z]+)*"message"(lottery.name.invalid}")

private String name; NotNull(message = "(lottery.age.absent)")

NotNull(message(lottery.mailid.absent)") @Pattern(regexp = "([a-z0-9]+)[@](infy gmail yahoo)(.com)",message "lottery.mailid.invalid)") private String mailld;

NotNull(message (lottery.contactno.absent)")

private Long contactio;

@NotNull(message = "(lottery.couponnumber.absent)") @Pattern(regexp = "[A-Z](3) [0-9](3)", message = "(lottery.couponnumber.invalid)")

private String couponfNumber; @NotNull(message"(lottery.winningamount.absent}")

12

13

14

15

private Integer age;

16

17

18

19

20

21

22

23

24-

25

26

27

28

29 30

31

324

34 354

36

37

BE

39 40

private Integer winningAmount; public Integer getParticipantId
