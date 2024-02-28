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
          {
              ParticipantDTO participantDTO=new ParticipantDTO();    
              participantDTO.setParticipantId(participant.getParticipantId()); 
              participantDTO.setName(participant.getName()); 
              participantDTO.setAge(participant.getAge());
              participantDTO.setMailId(participant.getMailId());
              participantDTO.setContactNo(participant.getContactNo()); 
              participantDTO.setCouponNumber(participant.getCouponNumber()); 
              participantDTO.setWinningAmount(participant.getWinningAmount()); 
              return participantDTO;
          }
          public static Participant prepareEntity (ParticipantDTO participantDTO){ 
                    Participant participant =new Participant(); 
                    participant.setName(participantDTO.getName());
                    participant.setAge(participantDTO.getAge()); 
                    participant.setMailId(participantDTO.getMailId()); 
                    participant.setContactNo(participantDTO.getContactNo()); 
                    participant.setCouponNumber(participantDTO.getCouponNumber()); 
                    participant.setWinningAmount(participantDTO.getWinningAmount()); 
                    return participant;
          }
</code></p>

**ParticipantValidator.java**
<p><code>
          public static void validateParticipant (ParticipantDTO participantDTO) throws LotteryBookingException {                                                   
                    if(isValidAge(participantDTO.getAge())==false)
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
                     
 **ParticipantRepository**  
 
<p><code>public interface ParticipantRepository extends CrudRepository<*Participant, Integer*> { 
          Participant findByCouponNumber (String coupon Number);
}
</code></P>

**ParticipantServiceImpl.java**
<p><code>
          <b>@Service(value="participantService")
          @Transactional</b>
          public class PraticipantServiceImpl implements ParticipantSerive{
                   <b> @Autowired</b>
                    private ParticipantRepository participantRepository;
          
                    @Override
                    public ParticipantDTO addParticipant(-----------){
                              ParticipantValidator.validateParticipant(participantDTO);
                              Participant participant=ParticipantDTO.prepareEntity(participantDTO);
                              participat=participantRepository.save(participant);
                              participantDTO.setParticipantId(participant.getParticipantId());
                              return participantDTO;
                    }

                    @Override
                    public ParticipantDTO getLotteryWinner(-----------){
                              Participant participant=ParticipantRepository.findByCouponNumber(couponNumber);
                              if(participant==null)
                              {
                                        throws new LotteryBookingException("ParticipantService.NO_PARTICIPANT_AVAILABLE");
                              }
                              ParticipantDTO participantDTO = PqrticipantDTO.prepareDTO(Participant); 
                              return participantDTO;
                    }
          }
</code></p>

**ExceptionControllerAdvice.java**
<p><code>
          @RestControllerAdvice
          public class ExceptionControllerAdvice{
                    @Autowired
                    private Environment environment;

                    @ExceptionHandler(LotteryBookingException.class)
                    public ResponseEntity<*ErrorInfor> lotteryBookingExceptionHandler(--------){
                    }
                    
                    @ExceptionHandler(Exception.class)
                    public ResponseEntity<*ErrorInfo> generalExceptionHandler(Exception exception)(
                    }

                    @ExceptionHandler({MethodArgumentNotValidException.class, ConstraintViolationException.class})
                    public ResponseEntity<*ErrorInfo> validatorExceptionhandler(Exception exception){
                    }                    
</code></p>
RequestMapping(value = "api")

@Validated

public class ParticipantAPI {

@Autowired

private ParticipantService participantService;

@GetMapping(value = "participant/{couponNumber)")

public ResponseEntity<ParticipantDTO> getLotteryWinner(@PathVariable @Pattern (regexp = "[A-Z]{3}[0-9]{3}", message = "{lottery.couponnumber.invalid}") @Valid String couponNumber) throws LotteryBookingException

{

ParticipantDTO dto participantService.getLotteryWinner(couponNumber); return new Response Entity<ParticipantDTO>(dto, HttpStatus.OK);

}

@PostMapping(value = "participants", consumes = "application/json")

public ResponseEntity<ParticipantDTO> addParticipant (@RequestBody @Valid ParticipantDTO participantDTO) throws LotteryBookingException{ ParticipantDTO participantDTO2= participantService.addParticipant (participantDTO);

return new Response Entity<ParticipantDTO>(participantDTO, HttpStatus.CREATED);

}
**ParticipatAPI.java**
<p><code>
          
</code></p>
