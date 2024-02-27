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
          private Integer participentId;
       <b> @NotNull(message="{lottery.name.absent}")
        @Pattern(regexp="[A-Za-z]+(\\s[A-Za-z]+)*",message="{lottery.name.invalid}")</b>
        private String name; 
         <b>@NotNull(message = "(lottery.age.absent)")</b>
          private Integer age;
         <b>@NotNull(message(lottery.mailid.absent)") 
          @Pattern(regexp = "([a-z0-9]+)[@](infy gmail yahoo)(.com)",message "lottery.mailid.invalid)")</b>
          private String mailld;
          NotNull(message (lottery.contactno.absent)")
          private Long contactio;
          @NotNull(message = "(lottery.couponnumber.absent)") 
          @Pattern(regexp = "[A-Z](3) [0-9](3)", message = "(lottery.couponnumber.invalid)")
          private String couponfNumber; 
          @NotNull(message"(lottery.winningamount.absent}")
          private Integer winningAmount; 
</code></p>
