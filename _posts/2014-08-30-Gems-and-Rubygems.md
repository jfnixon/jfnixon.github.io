---
layout: post
title: Ruby Gems
---

<div class="message">
To fully understand the Rails workflow, we need to understand the various tools.
Let's start with Ruby Gems.
</div>

## What are Ruby Gems?

Gems are simply a documented way of sharing Ruby code. Let's look at a gem!

{% highlight shell-session %}
2.1.2 penrose ~/test % gem list rake -r

*** REMOTE GEMS ***

airake (0.4.5)
airbrake (4.0.0)
[...]
rake (10.3.2)
rake-ar (1.0.0)
{% endhighlight %}

Download it and unpack it, and we'll see the rake executable, test code, source code, and 
metadata defining the authors, target platform, dependencies on other gems, and so forth. Gems are just
packages for sharing Ruby code and executables.

{% highlight shell-session %}
2.1.2 penrose ~/test % gem fetch rake
Fetching: rake-10.3.2.gem (100%)
Downloaded rake-10.3.2
2.1.2 penrose ~/test % ls
rake-10.3.2.gem
2.1.2 penrose ~/test % gem unpack rake
Unpacked gem: '/Users/jfnixon/test/rake-10.3.2'
2.1.2 penrose ~/test % ls
rake-10.3.2/     rake-10.3.2.gem
2.1.2 penrose ~/test % tree rake-10.3.2
rake-10.3.2
├── CONTRIBUTING.rdoc
├── History.rdoc
├── MIT-LICENSE
├── Manifest.txt
├── README.rdoc
├── Rakefile
├── bin
│   └── rake
├── doc
│   ├── command_line_usage.rdoc
│   ├── example
│   │   ├── Rakefile1
│   │   ├── Rakefile2
│   │   ├── a.c
│   │   ├── b.c
│   │   └── main.c
│   ├── glossary.rdoc
│   ├── jamis.rb
│   ├── proto_rake.rdoc
│   ├── rake.1.gz
│   ├── rakefile.rdoc
│   ├── rational.rdoc
│   └── release_notes
│       ├── rake-0.4.14.rdoc
│       ├── rake-0.4.15.rdoc
│       ├── rake-0.5.0.rdoc
│       ├── rake-0.5.3.rdoc
│       ├── rake-0.5.4.rdoc
│       ├── rake-0.6.0.rdoc
│       ├── rake-0.7.0.rdoc
│       ├── rake-0.7.1.rdoc
│       ├── rake-0.7.2.rdoc
│       ├── rake-0.7.3.rdoc
│       ├── rake-0.8.0.rdoc
│       ├── rake-0.8.2.rdoc
│       ├── rake-0.8.3.rdoc
│       ├── rake-0.8.4.rdoc
│       ├── rake-0.8.5.rdoc
│       ├── rake-0.8.6.rdoc
│       ├── rake-0.8.7.rdoc
│       ├── rake-0.9.0.rdoc
│       ├── rake-0.9.1.rdoc
│       ├── rake-0.9.2.2.rdoc
│       ├── rake-0.9.2.rdoc
│       ├── rake-0.9.3.rdoc
│       ├── rake-0.9.4.rdoc
│       ├── rake-0.9.5.rdoc
│       ├── rake-0.9.6.rdoc
│       ├── rake-10.0.0.rdoc
│       ├── rake-10.0.1.rdoc
│       ├── rake-10.0.2.rdoc
│       ├── rake-10.0.3.rdoc
│       └── rake-10.1.0.rdoc
├── lib
│   ├── rake
│   │   ├── alt_system.rb
│   │   ├── application.rb
│   │   ├── backtrace.rb
│   │   ├── clean.rb
│   │   ├── cloneable.rb
│   │   ├── contrib
│   │   │   ├── compositepublisher.rb
│   │   │   ├── ftptools.rb
│   │   │   ├── publisher.rb
│   │   │   ├── rubyforgepublisher.rb
│   │   │   ├── sshpublisher.rb
│   │   │   └── sys.rb
│   │   ├── cpu_counter.rb
│   │   ├── default_loader.rb
│   │   ├── dsl_definition.rb
│   │   ├── early_time.rb
│   │   ├── ext
│   │   │   ├── core.rb
│   │   │   ├── module.rb
│   │   │   ├── string.rb
│   │   │   └── time.rb
│   │   ├── file_creation_task.rb
│   │   ├── file_list.rb
│   │   ├── file_task.rb
│   │   ├── file_utils.rb
│   │   ├── file_utils_ext.rb
│   │   ├── gempackagetask.rb
│   │   ├── invocation_chain.rb
│   │   ├── invocation_exception_mixin.rb
│   │   ├── linked_list.rb
│   │   ├── loaders
│   │   │   └── makefile.rb
│   │   ├── multi_task.rb
│   │   ├── name_space.rb
│   │   ├── packagetask.rb
│   │   ├── pathmap.rb
│   │   ├── phony.rb
│   │   ├── private_reader.rb
│   │   ├── promise.rb
│   │   ├── pseudo_status.rb
│   │   ├── rake_module.rb
│   │   ├── rake_test_loader.rb
│   │   ├── rdoctask.rb
│   │   ├── ruby182_test_unit_fix.rb
│   │   ├── rule_recursion_overflow_error.rb
│   │   ├── runtest.rb
│   │   ├── scope.rb
│   │   ├── task.rb
│   │   ├── task_argument_error.rb
│   │   ├── task_arguments.rb
│   │   ├── task_manager.rb
│   │   ├── tasklib.rb
│   │   ├── testtask.rb
│   │   ├── thread_history_display.rb
│   │   ├── thread_pool.rb
│   │   ├── trace_output.rb
│   │   ├── version.rb
│   │   └── win32.rb
│   └── rake.rb
├── rakelib
│   ├── publish.rake
│   └── test_times.rake
└── test
    ├── file_creation.rb
    ├── helper.rb
    ├── support
    │   ├── rakefile_definitions.rb
    │   └── ruby_runner.rb
    ├── test_private_reader.rb
    ├── test_rake.rb
    ├── test_rake_application.rb
    ├── test_rake_application_options.rb
    ├── test_rake_backtrace.rb
    ├── test_rake_clean.rb
    ├── test_rake_cpu_counter.rb
    ├── test_rake_definitions.rb
    ├── test_rake_directory_task.rb
    ├── test_rake_dsl.rb
    ├── test_rake_early_time.rb
    ├── test_rake_extension.rb
    ├── test_rake_file_creation_task.rb
    ├── test_rake_file_list.rb
    ├── test_rake_file_list_path_map.rb
    ├── test_rake_file_task.rb
    ├── test_rake_file_utils.rb
    ├── test_rake_ftp_file.rb
    ├── test_rake_functional.rb
    ├── test_rake_invocation_chain.rb
    ├── test_rake_linked_list.rb
    ├── test_rake_makefile_loader.rb
    ├── test_rake_multi_task.rb
    ├── test_rake_name_space.rb
    ├── test_rake_package_task.rb
    ├── test_rake_path_map.rb
    ├── test_rake_path_map_explode.rb
    ├── test_rake_path_map_partial.rb
    ├── test_rake_pseudo_status.rb
    ├── test_rake_rake_test_loader.rb
    ├── test_rake_reduce_compat.rb
    ├── test_rake_require.rb
    ├── test_rake_rules.rb
    ├── test_rake_scope.rb
    ├── test_rake_task.rb
    ├── test_rake_task_argument_parsing.rb
    ├── test_rake_task_arguments.rb
    ├── test_rake_task_lib.rb
    ├── test_rake_task_manager.rb
    ├── test_rake_task_manager_argument_resolution.rb
    ├── test_rake_task_with_arguments.rb
    ├── test_rake_test_task.rb
    ├── test_rake_thread_pool.rb
    ├── test_rake_top_level_functions.rb
    ├── test_rake_win32.rb
    ├── test_thread_history_display.rb
    └── test_trace_output.rb

12 directories, 158 files
2.1.2 penrose ~/test %
{% endhighlight %}
