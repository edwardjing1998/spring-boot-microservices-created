import lombok.Getter;
import lombok.RequiredArgsConstructor;
import lombok.NoArgsConstructor;
import lombok.AccessLevel;

import java.time.LocalDateTime;

@Getter
@RequiredArgsConstructor
@NoArgsConstructor(force = true, access = AccessLevel.PROTECTED)
public class AdminQueryListDTO {

    private final Integer     reportId;
    private final String      queryName;
    private final String      query;
    private final String      inputDataFields;
    private final String      fileExt;
    private final String      dbDriverType;
    private final Integer     fileHeaderInd;
    private final String      defaultFileNm;
    private final String      reportDbServer;
    private final String      reportDb;
    private final String      reportDbUserid;
    private final String      reportDbPasswrd;
    private final Integer     fileTransferType;
    private final String      reportDbIpAndPort;
    private final Boolean     reportByClientFlag;
    private final LocalDateTime rerunDateRangeStart;
    private final LocalDateTime rerunDateRangeEnd;
    private final String      rerunClientId;
    private final String      emailFromAddress;
    private final String      emailEventId;
    private final Boolean     tabDelimitedFlag;
    private final String      inputFileTx;
    private final Integer     inputFileKeyStartPos;
    private final Integer     inputFileKeyLength;
    private final Byte        accessLevel;
    private final Boolean     isActive;
    private final Boolean     isVisible;
    private final Integer     numSheets;

    /** Factory method — the mapping logic lives here */
    public static AdminQueryListDTO from(AdminQueryList e) {
        return new AdminQueryListDTO(
            e.getReportId(),
            e.getQueryName(),
            e.getQuery(),
            e.getInputDataFields(),
            e.getFileExt(),
            e.getDbDriverType(),
            e.getFileHeaderInd(),
            e.getDefaultFileNm(),
            e.getReportDbServer(),
            e.getReportDb(),
            e.getReportDbUserid(),
            e.getReportDbPasswrd(),
            e.getFileTransferType(),
            e.getReportDbIpAndPort(),
            e.getReportByClientFlag(),
            e.getRerunDateRangeStart(),
            e.getRerunDateRangeEnd(),
            e.getRerunClientId(),
            e.getEmailFromAddress(),
            e.getEmailEventId(),
            e.getTabDelimitedFlag(),
            e.getInputFileTx(),
            e.getInputFileKeyStartPos(),
            e.getInputFileKeyLength(),
            e.getAccessLevel(),
            e.getIsActive(),
            e.getIsVisible(),
            e.getNumSheets()
        );
    }
}
