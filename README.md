import org.springframework.beans.factory.annotation.Value;
import org.springframework.jdbc.core.namedparam.MapSqlParameterSource;
import org.springframework.jdbc.core.namedparam.NamedParameterJdbcTemplate;
import org.springframework.stereotype.Repository;

@Repository
public class ClientJsonDaoFromConfig {

  private final NamedParameterJdbcTemplate jdbc;

  public ClientJsonDaoFromConfig(NamedParameterJdbcTemplate jdbc) {
    this.jdbc = jdbc;
  }

  @Value("${rapid.sql.fetchFullJson}")
  private String fetchFullJsonSql;

  public String fetchFullJsonPage(int offset, int size) {
    var params = new MapSqlParameterSource()
        .addValue("size", size)
        .addValue("offset", offset);
    return jdbc.queryForObject(fetchFullJsonSql, params, String.class);
  }
}





    @Filter(type = FilterType.ASSIGNABLE_TYPE, classes = {
      rapid.repository.legacy.LegacyClientRepository.class,
      rapid.repository.experimental.ExperimentalRepo.class
    }),
