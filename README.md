@RestController
@CrossOrigin(origins = { "*" })
@SpringBootApplication
@EntityScan("rapid.model")
@EnableJpaRepositories(
        basePackages = "rapid",
        excludeFilters = {
        // Exclude by concrete type(s)
        @ComponentScan.Filter(type = FilterType.ASSIGNABLE_TYPE, classes = {
                rapid.repository.client.ClientDetailDaoWithNativeSql.class
        }),
})
