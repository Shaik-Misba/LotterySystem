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
