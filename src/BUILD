lex_yacc_library(
     name = 'parser',
     srcs = [ 
         'scan.ll',
         'parse.yy',
     ],  
     deps = [ 
     ],  
     #recursive = True
)
cc_library(
  name = "pf",
  srcs = [
    "pf_buffermgr.cc",
    "pf_error.cc",
    "pf_filehandle.cc",
    "pf_pagehandle.cc",
    "pf_hashtable.cc",
    "pf_manager.cc",
    "pf_statistics.cc",
    "statistics.cc",
  ]
)

cc_library(
  name = "rm",
  srcs = [
    "rm_filehandle.cc",
    "rm_manager.cc",
    "rm_record.cc",
    "rm_rid.cc",
    "rm_filescan.cc",
    "rm_printerror.cc",
  ]
)

cc_library(
  name = "ix",
  srcs = [
    "ix_indexhandle.cc",
    "ix_indexscan.cc",
    "ix_manager.cc",
    "ix_printerror.cc",
  ],
)

cc_library(
  name = "sm",
  srcs = [
    "sm_manager.cc",
    "printer.cc",
    "sm_printerror.cc",
  ]
)

cc_library(
  name = "ql",
  srcs = [
    "ql_manager.cc",
    "ql_operators.cc",
    "ql_printerror.cc",
    "ex_abhinav.cc",
  ],
  deps = [
    ":rm",
    ":sm",
    ":ix",
    ":pf",
  ],
)

cc_library(
  name = "pr",
  srcs = [
    "scan.cc",
    "nodes.cc",
    "interp.cc",
  ]
)

cc_binary(
  name = "redbase",
  srcs = [
    "redbase.cc",
  ],
  deps = [
    ":parser",
    ":pr",
    ":pf",
    ":rm",
    ":ix",
    ":ql",
  ],
)

cc_binary(
  name = "dbcreate",
  srcs = [
    "dbcreate.cc",
  ],
  deps = [
    ":parser",
    ":pr",
    ":pf",
    ":rm",
    ":ix",
    ":ql",
  ],
)

cc_binary(
  name = "dbdestroy",
  srcs = [
    "dbdestroy.cc",
  ],
  deps = [
    ":parser",
    ":pr",
    ":pf",
    ":rm",
    ":ix",
    ":ql",
  ],
)
