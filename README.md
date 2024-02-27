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

          }

public static ParticipantDTO prepareDTO(Participant participant)

ParticipantDTO participantDTO=new ParticipantDTO(); participantDTO.setParticipantId(participant.getParticipantId()); participantDTO.setName(participant.getName()); participantDTO.setAge(participant.getAge()); participantDTO, setMailId(participant.getMailId()); participantDTO.setContactNo(participant.getContactNo()); participantDTO.setCouponNumber(participant.getCouponNumber()); participantDTO.setWinningAmount(participant.getWinningAmount()); return participantDTO;

}

public static Participant prepareEntity (ParticipantDTO participantDTO){ Participant participant =new Participant(); participant.setName(participantDTO.getName()); participant.setAge(participantDTO.getAge()); participant.setMailId(participantDTO.getMailId()); participant.setContactNo(participantDTO.getContactNo()); participant.setCouponNumber(participantDTO.getCouponNumber()); participant.setWinningAmount(participantDTO.getWinningAmount()); return participant;

}
</code></p>

**ParticipantValidator.java**
<p><code>public static void validateParticipant (ParticipantDTO participantDTO) throws LotteryBookingException {                       if(isValidAge(participantDTO.getAge())==false)
          {
                  throw new LotteryBookingException("ParticipantValidator.INVALID_AGE");
          }
}
public static Boolean isValidAge(Integer age) 
{
           if(age<18){
                   return false;
           }
           return true;
}
</code></p>
          
public interface ParticipantRepository extends CrudRepository<Participant, Integer> { Participant findByCoupon Number (String coupon Nuumber);

}
