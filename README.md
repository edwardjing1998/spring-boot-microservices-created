@RestController
@CrossOrigin(origins = {"*"})
@SpringBootApplication(scanBasePackages = {
        "rapid"
})
@EntityScan("rapid.model")
@EnableJpaRepositories("rapid.repository")
