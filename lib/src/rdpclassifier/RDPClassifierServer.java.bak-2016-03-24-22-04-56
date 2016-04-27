package rdpclassifier;

import java.io.File;
import us.kbase.common.service.JsonServerServlet;
import us.kbase.common.service.JsonServerSyslog;

//BEGIN_HEADER
//END_HEADER

/**
 * <p>Original spec-file module name: RDPClassifier</p>
 * <pre>
 * A KBase module: RDPClassifier
 * </pre>
 */
public class RDPClassifierServer extends JsonServerServlet {
    private static final long serialVersionUID = 1L;

    //BEGIN_CLASS_HEADER
    //END_CLASS_HEADER

    public RDPClassifierServer() throws Exception {
        super("RDPClassifier");
        //BEGIN_CONSTRUCTOR
        //END_CONSTRUCTOR
    }

    public static void main(String[] args) throws Exception {
        if (args.length == 1) {
            new RDPClassifierServer().startupServer(Integer.parseInt(args[0]));
        } else if (args.length == 3) {
            JsonServerSyslog.setStaticUseSyslog(false);
            JsonServerSyslog.setStaticMlogFile(args[1] + ".log");
            new RDPClassifierServer().processRpcCall(new File(args[0]), new File(args[1]), args[2]);
        } else {
            System.out.println("Usage: <program> <server_port>");
            System.out.println("   or: <program> <context_json_file> <output_json_file> <token>");
            return;
        }
    }
}
