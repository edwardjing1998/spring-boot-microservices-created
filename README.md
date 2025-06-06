package admin.dto;

import admin.model.AdminQueryList;
import jdk.jfr.Name;
import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

import java.time.LocalDateTime;

@Data
@NoArgsConstructor
@AllArgsConstructor
public class AdminQueryListDTO {

    public AdminQueryListDTO(AdminQueryList entity) {
        this.reportId = entity.getReportId();
        this.queryName = entity.getQueryName();
        this.query = entity.getQuery();
        this.inputDataFields = entity.getInputDataFields();
        this.fileExt = entity.getFileExt();
        this.dbDriverType = entity.getDbDriverType();
        this.fileHeaderInd = entity.getFileHeaderInd();
        this.defaultFileNm = entity.getDefaultFileNm();
        this.reportDbServer = entity.getReportDbServer();
        this.reportDb = entity.getReportDb();
        this.reportDbUserid = entity.getReportDbUserid();
        this.reportDbPasswrd = entity.getReportDbPasswrd();
        this.fileTransferType = entity.getFileTransferType();
        this.reportDbIpAndPort = entity.getReportDbIpAndPort();
        this.reportByClientFlag = entity.getReportByClientFlag();
        this.rerunDateRangeStart = entity.getRerunDateRangeStart();
        this.rerunDateRangeEnd = entity.getRerunDateRangeEnd();
        this.rerunClientId = entity.getRerunClientId();
        this.emailFromAddress = entity.getEmailFromAddress();
        this.emailEventId = entity.getEmailEventId();
        this.tabDelimitedFlag = entity.getTabDelimitedFlag();
        this.inputFileTx = entity.getInputFileTx();
        this.inputFileKeyStartPos = entity.getInputFileKeyStartPos();
        this.inputFileKeyLength = entity.getInputFileKeyLength();
        this.accessLevel = entity.getAccessLevel();
        this.isActive = entity.getIsActive();
        this.isVisible = entity.getIsVisible();
        this.numSheets = entity.getNumSheets();
    }


    private final Integer reportId;
    private final String queryName;
    private final String query;
    private final String inputDataFields;
    private final String fileExt;
    private String dbDriverType;
    private Integer fileHeaderInd;
    private String defaultFileNm;
    private String reportDbServer;
    private String reportDb;
    private String reportDbUserid;
    private String reportDbPasswrd;
    private Integer fileTransferType;
    private String reportDbIpAndPort;
    private Boolean reportByClientFlag;
    private LocalDateTime rerunDateRangeStart;
    private LocalDateTime rerunDateRangeEnd;
    private String rerunClientId;
    private String emailFromAddress;
    private String emailEventId;
    private Boolean tabDelimitedFlag;
    private String inputFileTx;
    private Integer inputFileKeyStartPos;
    private Integer inputFileKeyLength;
    private Byte accessLevel;
    private Boolean isActive;
    private Boolean isVisible;
    private Integer numSheets;
}
