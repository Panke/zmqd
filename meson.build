project('zmqd', 'd')

zeromq_dep = dependency('zeromq',
    version: '>=6.1',
    fallback: ['zeromq', 'zeromq_dep'])

zmqd_source_dep = declare_dependency(
    include_directories: 'src',
    dependencies: zeromq_dep,
    version: meson.project_version()
)

deimos_zeromq_dep = dependency('zeromq', fallback: ['deimos-zeromq', 'deimos_zeromq_source_dep'])

examples = [
   'hwclient.d',
   'hwserver.d',
   'identity.d',
   'msgqueue.d',
   'mspoller.d',
   'msreader.d',
   'mtrelay.d',
   'mtserver.d',
   'rrbroker.d',
   'rrclient.d',
   'rrworker.d',
   'rtdealer.d',
   'rtreq.d',
   'tasksink2.d',
   'tasksink.d',
   'taskvent.d',
   'taskwork2.d',
   'taskwork.d',
   'test_metadata.d',
   'version.d',
   'wuclient.d',
   'wuserver.d',
]

foreach x :  examples
	executable(x, './examples/' + x,
 	d_args: ['-i'],
	include_directories: './examples', # zhelpers
	dependencies: [zmqd_source_dep])
endforeach
