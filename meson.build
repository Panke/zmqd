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
   'hwclient',
   'hwserver',
   'identity',
   'interrupt',
   'lbbroker',
   'lbbroker2',
   'msgqueue',
   'mspoller',
   'msreader',
   'mtrelay',
   'mtserver',
   'rrbroker',
   'rrclient',
   'rrworker',
   'rtdealer',
   'rtreq',
   'syncpub',
   'syncsub',
   'psenvpub',
   'psenvsub',
   'tasksink2',
   'tasksink',
   'taskvent',
   'taskwork2',
   'taskwork',
   'test_metadata',
   'version',
   'wuclient',
   'wuproxy',
   'wuserver'
]

foreach x : examples
	executable(x, './examples/' + x + '.d',
    	d_args: ['-i'],
        include_directories: './examples', # zhelpers
        dependencies: [zmqd_source_dep]
	)
endforeach
