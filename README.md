  excludeFilters = {
    // Exclude by concrete type(s)
    @Filter(type = FilterType.ASSIGNABLE_TYPE, classes = {
      rapid.repository.legacy.LegacyClientRepository.class,
      rapid.repository.experimental.ExperimentalRepo.class
    }),
    // Or exclude whole package(s) by regex
    @Filter(type = FilterType.REGEX, pattern = "rapid\\.repository\\.temp\\..*"),
    // Or exclude everything marked with a custom annotation
    @Filter(type = FilterType.ANNOTATION, classes = ExcludeFromRepositoryScan.class)
  }
