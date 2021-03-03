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
   'examples/hwclient.d',
   'examples/hwserver.d',
   'examples/identity.d',
   'examples/interrupt.d',
   'examples/msgqueue.d',
   'examples/mspoller.d',
   'examples/msreader.d',
   'examples/mtrelay.d',
   'examples/mtserver.d',
   'examples/rrbroker.d',
   'examples/rrclient.d',
   'examples/rrworker.d',
   'examples/rtdealer.d',
   'examples/rtreq.d',
   'examples/syncpub.d',
   'examples/syncsub2.d',
   'examples/syncsub.d',
   'examples/tasksink2.d',
   'examples/tasksink.d',
   'examples/taskvent.d',
   'examples/taskwork2.d',
   'examples/taskwork.d',
   'examples/test_metadata.d',
   'examples/version.d',
   'examples/wuclient.d',
   'examples/wuproxy.d',
   'examples/wuserver.d'
]

foreach x : examples
	executable(x, './examples/' + x,
    	d_args: ['-i'],
   	include_directories: './examples', # zhelpers
   	dependencies: [zmqd_source_dep]
	)
endforeach
