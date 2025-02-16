# News

## 3.0.5 - 2014-11-08 {#version-3-0-5}

It's a minor update release.

### Fixes

  * Fixed a bug that startup/shutdown of parent test case isn't called
    when the test case includes one or more modules.
    [GitHub#83][Reported by Chadderton Odwazny]

### Thanks

  * Chadderton Odwazny

## 3.0.4 - 2014-11-01 {#version-3-0-4}

It's a minor update release.

### Improvements

  * Stopped to remove JRuby and Rubinius internal backtrace entries from
    backtrace on failure/error.
    [GitHub#82][Patch by Charles Oliver Nutter]

### Thanks

  * Charles Oliver Nutter

## 3.0.3 - 2014-10-29 {#version-3-0-3}

It's a minor update release.

### Improvements

  * Improved `Test::Unit::TestCase.test` performance.
    100 times faster.
  * Supported `Proc` for user message.
    [Sugested by Nobuyoshi Nakada]

### Fixes

  * Fixed markup in document.
    [GitHub#81][Patch by Masafumi Yokoyama]

### Thanks

  * Masafumi Yokoyama
  * Nobuyoshi Nakada

## 3.0.2 - 2014-10-15 {#version-3-0-2}

It's a minor update release.

### Improvements

  * Supported broken `==` implementation.
    `==` implementation should be fixed but it's not work of test-unit. :<
    [GitHub#71][Reported by Emily]
  * [UI][console]: Accepted no message failure.
    [GitHub#66][Reported by Brian Tatnall]
  * Updated gem description.
    [GitHub#74][Patch by Vít Ondruch]
  * Updated GPL text.
    [GitHub#78][Patch by Vít Ondruch]

### Fixes

  * Removed needless executable bit from README file.
    [GitHub#79][Patch by Vít Ondruch]

### Thanks

  * Emily
  * Brian Tatnall
  * Vít Ondruch

## 3.0.1 - 2014-08-05 {#version-3-0-1}

It's a minor update release.

### Improvements

  * Improved Ruby 1.8.7 support. Note that we don't support Ruby 1.8.7
    actively. We just support if its support is painless.
    [GitHub#71][Patch by estolfo]

### Thanks

  * estolfo

## 3.0.0 - 2014-08-03 {#version-3-0-0}

It's Power Assert supported release!

### Improvements

  * Improved Rubinius support. [Ryo Onodera]
  * Updated RR repository link. [GitHub#56][Patch by Kenichi Kamiya]
  * Added some minitest compatible assertions. We don't recommend
    using these assertions. They are just for migrating from minitest.
    [GitHub#57][Patch by Karol Bucek]
    * {Test::Unit::Assertions#refute}
    * {Test::Unit::Assertions#refute_predicate}
    * {Test::Unit::Assertions#refute_empty}
    * {Test::Unit::Assertions#assert_not_includes}
    * {Test::Unit::Assertions#refute_includes}
    * {Test::Unit::Assertions#assert_not_instance_of}
    * {Test::Unit::Assertions#refute_instance_of}
    * {Test::Unit::Assertions#assert_not_kind_of}
    * {Test::Unit::Assertions#refute_kind_of}
    * {Test::Unit::Assertions#assert_not_operator}
    * {Test::Unit::Assertions#refute_operator}
  * Improved code readability. [Suggested by Kenichi Kamiya]
  * Made license field in RubyGems parseable.
    [GitHub#60][Patch by Michael Grosser]
  * Improved test case match feature by `--testcase` and `--ignore-testcase`
    options. They also checks parent class names.
  * Made inspected representation of Numeric objects especially
    BigDecimal more readable. [GitHub#64][Reported by Byron Appelt]
  * Added badges for Traivs CI and RubyGems.
    [GitHub#65][Patch by Byron Appelt]
  * Supported Power Assert. You can use Power Assert with
    {Test::Unit::Assertions#assert} with block. See method document
    for details. We recommend using Power Assert for predicate method
    checks. For example, we recommend Power Assert rather than
    {Test::Unit::Assertions#assert_true},
    {Test::Unit::Assertions#assert_predicate} and so on. We don't
    recommend using Power Assert for equality check assertion.
    {Test::Unit::Assertions#assert_equal} should be used for the case.
    [Kazuki Tsujimoto]

### Fixes

  * Fixed a bug that test case defined by block has wrong location.
    [GitHub#58][Patch by Narihiro Nakamura]
  * Fixed a bug that test methods defined in included modules in
    super-class are also collected.
    [GitHub#62][GitHub#63][Patch by Karol Bucek]

### Thanks

  * Ryo Onodera
  * Kenichi Kamiya
  * Karol Bucek
  * Narihiro Nakamura
  * Michael Grosser
  * Byron Appelt
  * Kazuki Tsujimoto

## 2.5.5 - 2013-05-18 {#version-2-5-5}

It's Ruby 2.0.0 supported release!

### Improvements

  * Supported Ruby 2.0.0. [GitHub#54] [Reported by mtasaka]
  * Accepted screen-256color TERM as 256 colors available environment.
    [GitHub#55] [Reported by Tom Miller]

### Fixes

  * Fixed a typo in document.
    [GitHub#53] [Patch by Baptiste Fontaine]
  * Fixed a bug in {Test::Unit::Assertions#assert_in_epsilon}. It doesn't work
    as expected if expected value is negative value.
    [Ruby Bug #8317] [Reported by Nobuhiro IMAI]

### Thanks

  * Baptiste Fontaine
  * mtasaka
  * Tom Miller
  * Nobuhiro IMAI

## 2.5.4 - 2013-01-23 {#version-2-5-4}

It's a bug fix release.

### Improvements

  * Added documents for data driven test functionality.
  * Added TSV support for data driven test functionality.
  * Support tag inspection on JRuby.

### Fixes

  * Fixed a bug. It is too slow to filter tests when there are many
    tests. [GitHub#46]
  * Accept anonymous test suite.
    [GitHub:#49] [Reported by Matthew Rudy Jacobs]

### Thanks

  * Matthew Rudy Jacobs

## 2.5.3 - 2012-11-28 {#version-2-5-3}

It's a release for minitest compatibility and bug fix.

### Improvements

  * Supported diff in invalid encoding.
  * Added some assersion methods just for minitest compatibility.
    Added methods are assert_includes(), refute_*() and refute().
    If you are test-unit user, please don't use them.
    [GitHub#40] [Suggested by Michael Grosser]
  * Added --attribute option to select target tests by attribute.
    [test-unit-users-en:00098] [Suggested by Piotr Nestorow]

### Fixes

  * Allowed use of test for inheritance in ActionController::TestCase.
    [GitHub#42] [Patch by David Rasch]
  * Ensured evaluating at_exist block in top level.
    In IRB context, exit() specifies irb_exit().
    [test-unit-users-en:00089] [Reported by Daniel Berger]
  * Fixed a bug that decoration style description is ignored.
    "decoration style description" are using description method
    above "def test_name" or with Symbol specifying test_name.
    [GitHub#45] [Reported by Piotr Nestorow]

### Thanks

  * Michael Grosser
  * David Rasch
  * Daniel Berger
  * Piotr Nestorow

## 2.5.2 - 2012-08-29 {#version-2-5-2}

It's an improvement release for tmtms. `--location` is a similar
feature to `--line_number` in RSpec. `sub_test_case` is a similar
feature to `context` in shoulda-context and RSpec.

### Improvements

  * Cleaned up tests.
    [GitHub#34] [Patch by Michael Grosser]
  * Added missing background color for 8 color environment.
  * Added workaround for NetBeans.
    [GitHub#38] [Reported by Marc Cooper]
  * Added `--location` command line option that selects target tests
    by test defined location.
  * Created sub test suite for each subclassed test case.
  * [ui][console] Supported nested test suites.
  * Added {Test::Unit.at_start} and {Test::Unit.at_exit} hooks that
    are run before/after all tests are run.
    [Good hook name is suggested by kdmsnr]
  * Improved code snippet target on failure. Test method is always used
    for code snippet target.
    [GitHub#39] [Suggested by Michael Grosser]
  * Added {Test::Unit::TestCase.sub_test_case} that creates sub test case.
    The sub test case name isn't limited Ruby's constant name rule. You can
    specify the sub test case name in free form.

### Thanks

  * Michael Grosser
  * Marc Cooper
  * kdmsnr

## 2.5.1 - 2012-07-05 {#version-2-5-1}

It's a bug fix release.

### Improvements

  * Supported installing from GitHub.
    [GitHub#29] [Suggested by Michael Grosser]
  * Supported ActiveSupport::TestCase.
    [GitHub#30] [Reported by Michael Grosser]
  * [ui][console] Improved multiline falut message display.

### Fixes

  * [ui][console] Fixed a bug that expected and actual values are
    empty.
    [GitHub#31][GitHub#33]
    [Reported by Kendall Buchanan][Reported by Mathieu Martin]
    [Hinted by Michael Grosser]
  * Fixed a bug that .gemspec can't be loaded on LANG=C.
    [RubyForge#29595] [Reported by Jean-Denis Koeck]

### Thanks

  * Michael Grosser
  * Kendall Buchanan
  * Mathieu Martin
  * Jean-Denis Koeck

## 2.5.0 - 2012-06-06 {#version-2-5-0}

It's a bug fix release.

### Fixes

  * Fixed a backward incompatibility of `TestUnitMediator#run_suite`
    introduced in 2.4.9.
    [GitHub#28] [Reported by Vladislav Rassokhin]

### Thanks

  * Vladislav Rassokhin

## 2.4.9 - 2012-06-03 {#version-2-4-9}

It's a bug fix release.

### Improvements

  * `Test::Unit.run?` ->
    `Test::Unit::AutoRunner.need_auto_run?`. `Test::Unit.run?` is marked
    as deprecated but it is still available.
  * [experimental] Added top level "run" method for `"ruby -rtest-unit -e
    run test/test_*.rb"`. Is this API OK or dirty?
  * Made failure output more readable on no color mode.
  * Supported showing ASCII-8BIT diff in failure message.
  * [ui][console] Supported `ENV["TERM"] == "xterm-256color"` as color
    available terminal.
    [GitHub#26] [Reported by Michael Grosser]
  * [ui][console] Supported "-256color" suffix `ENV["TERM"]` terminal
    as 256 color supported terminal.

### Fixes

  * Fixed a bug that `--workdir` doesn't work.
  * Consumed processed command line parameters in `ARGV` as `--help`
    says.
    [RubyForge#29554] [Reported by Bob Saveland]
  * Added missing `require "test/unit/diff"`.
    [GitHub#25] [Reported by Stephan Kulow]

### Thanks

  * Bob Saveland
  * Stephan Kulow
  * Michael Grosser

## 2.4.8 - 2012-3-6 {#version-2-4-8}

It's a bug fix release.

### Improvements

  * Delayed at_exit registration until Test::Unit is used.
    [GitHub:#21] [Reported by Jason Lunn]
  * Added workaround for test-spec.
    [GitHub:#22] [Reported by Cédric Boutillier]

### Fixes

  * Fixed an error on code snippet display on JRuby.
    [GitHub:#19][GitHub:#20]
    [Reported by Jørgen P. Tjernø][Patch by Junegunn Choi]

### Thanks

  * Jørgen P. Tjernø
  * Junegunn Choi
  * Jason Lunn

## 2.4.7 - 2012-2-10 {#version-2-4-7}

It's a code snippet improvement release.

### Improvements

  * Supported code snippet display on all faults.

## 2.4.6 - 2012-2-9 {#version-2-4-6}

It's a TAP runner separated release.

### Improvements

  * Moved TAP runner to test-unit-runner-tap gem from test-unit gem.
  * Supported code snippet display on failure.

## 2.4.5 - 2012-1-16 {#version-2-4-5}

It's a failure message readability improvement release.

### Improvements

  * Removed needless information from exception inspected
    text on failure. It's for easy to read.
  * Supported custom inspector.

## 2.4.4 - 2012-1-2 {#version-2-4-4}

It's a Rails integration improved release.

### Improvements

  * [ui][console] Don't break progress display when a test is failed.
  * [ui][console] Added markers betwen a failure detail
    message in progress to improve visibility.
  * [travis] Dropped Ruby 1.8.6 as a test target. [GitHub:#13]
    [Patch by Josh Kalderimis]
  * Supported expected value == 0 case in assert_in_epsilon. [RubyForge#29485]
    [Reported by Syver Enstad]
  * Supported a block style setup/teardown/cleanup.

### Thanks

  * Josh Kalderimis
  * Syver Enstad

## 2.4.3 - 2011-12-11 {#version-2-4-3}

### Improvements

  * Improved SimpleCov integration by stopping to modify
    `ARGV` in auto runner. [GitHub:#12]
    [Reported by Nikos Dimitrakopoulos]
  * Improved JRuby integration by removing JRuby internal backtrace.

### Thanks

  * Nikos Dimitrakopoulos

## 2.4.2 - 2011-11-26 {#version-2-4-2}

### Improvements

  * `--name` supported data label.

## 2.4.1 - 2011-11-09

### Improvements

  * Accepted AssertionMessage as assertion's user message.
    It is used in assert_select in actionpack.
    [Reported by David Heath]

### Fixes

  * Fixed test failure on LANG=C. #11 [Reported by boutil]
  * Suppress warnings on Ruby 1.9.2.

### Thanks

  * boutil
  * David Heath

## 2.4.0 - 2011-09-18

### Improvements

  * Supported Travis CI. #5 [Suggested by James Mead]
  * Added Gemfile. #6 [Suggested by James Mead]
  * [ui][console] Supported notification in show-detail-immediately.
  * [ui][console] enable --show-detail-immediately by default.
  * [ui] Added --max-diff-target-string-size option.
  * [ui][console] Supported 256 colors.

### Fixes

  * Added missing fixture file. #7 [Reported by grafi-tt]
  * [ui][console] Added missing the last newline for progress level.
  * Supported correct backtrace for redefined notification.
  * Don't handle Timeout::Error as pass through exception on Ruby 1.8. #8
    [Reported by Marc Seeger (Acquia)]

### Thanks

  * James Mead
  * grafi-tt
  * Marc Seeger (Acquia)

## 2.3.2 - 2011-08-15

A bug fix release.

### Improvements

  * [ui][console] Added some newlines to improve readability.

### Fixes

  * [ui][console] Worked --verbose again.
  * Re-supported Ruby 1.8.6. [Reported by James Mead]

### Thanks

  * James Mead

## 2.3.1 - 2011-08-06 {#version-2-3-1}

Output improvement release!

### Improvements

  * [ui][console] Outputs omissions and notifications in short.
  * [ui][console] Added "important-only" verbose level.
  * Intelligence diff supports recursive references.
  * [rubyforge #29325] Supported Ruby Enterprise Edition.
    [Reported by Hans de Graaff]
  * [rubyforge #29326] Supported JRuby.
    [Reported by Hans de Graaff]
  * Added --show-detail-immediately option that shows
    fault details when a fault is occurred.

### Fixes

  * [pull request #1] Fixed a problem that load collector
    can't load a test file on Ruby 1.9. [Patch by grafi-tt]
  * [issue #3] Fixed a problem that implicit method name
    override by declarative style test definition.
    [Reported by Jeremy Stephens]

### Thanks

  * grafi-tt
  * Jeremy Stephens
  * Hans de Graaff

## 2.3.0 / 2011-04-17

* 13 enhancements
  * improve Hash key sorting for diff.
  * [#28928] support any characters in declarative style description.
    [Daniel Berger]
  * add Error#location and make #backtrace deprecated.
  * make TestCase#passed? public.
  * add result finished and pass assertion notifications.
  * add TestSuite#passed? public.
  * add XML test runner.
  * add --output-file-descriptor option.
  * measure elapsed time for each test.
  * add --collector option.
  * support test driven test.
    [Haruka Yoshihara]
  * add cleanup hook it runs between after test and before teardown.
  * support recursive collection sort for diff.

* Thanks
  * Daniel Berger
  * Haruka Yoshihara

## 2.2.0 / 2011-02-14

* 22 enhancements
  * [#28808] accept String as delta for assert_in_delta.
    [Daniel Berger]
  * [test-unit-users-en:00035] make GC-able finished tests.
    [Daniel Berger]
  * use also COLUMNS environment variable to guess terminal width.
  * make delta for assert_in_delta optional.
    [Nobuyoshi Nakada]
  * add assert_not_respond_to.
    [Nobuyoshi Nakada]
  * add assert_not_match. assert_no_match is deprecated.
    [Nobuyoshi Nakada]
  * add assert_not_in_delta.
    [Nobuyoshi Nakada]
  * add assert_in_epsilon.
    [Nobuyoshi Nakada]
  * add assert_not_in_epsilon.
    [Nobuyoshi Nakada]
  * add assert_include.
    [Nobuyoshi Nakada]
  * add assert_not_include.
    [Nobuyoshi Nakada]
  * add assert_empty.
    [Nobuyoshi Nakada]
  * add assert_not_empty.
    [Nobuyoshi Nakada]
  * notify require failed paths.
  * validate message value for assert.
  * show throughputs at the last.
  * support not ASCII compatible string diff.
  * support colorized diff on encoding different string.
  * normalize entry order of Hash for readable diff.
  * add --ignore-name option.
  * add --ignore-testcase option.
  * add assert_not_send.

* Thanks
  * Daniel Berger
  * Nobuyoshi Nakada

## 2.1.2 / 2010-11-25

* 1 enhancement
  * support auto runner prepare hook.

## 2.1.1 / 2010-07-29

* 1 bug fix
  * [test-unit-users-en:00026] re-work tap runner.
    [Daniel Berger]

* Thanks
  * Daniel Berger

=== 2.1.0 / 2010-07-17

* 1 bug fix
  * [#28267] global config file ignored
    [Daniel Berger]

* Thanks
  * Daniel Berger

## 2.0.8 / 2010-06-02

* 5 major enchancements
  * collect *_test.rb and *-test.rb files as test files.
  * [#28181] improve assert_in_delta message.
    [Suggested by David MARCHALAND]
  * show string encoding in assert_equal failure message if
    they are different.
  * change default color scheme:
    * success: green back + white
    * failure: red back + white
  * add capture_output.

* 2 bug fixes
  * fix a bug that console runner on verbose mode causes an
    error for long test name (>= 61).
  * [#28093] Autorunner ignores all files in a directory named test by default
    [Reported by Florian Frank]

* Thanks
  * Florian Frank
  * David MARCHALAND

## 2.0.7 / 2010-03-09

* 4 major enhancements
  * detect redefined test methods.
  * [INTERFACE IMCOMPATIBLE] multiple --name and --testcase
    options narrow down targets instead of adding targets.
  * [#27764] accept custom test_order for each test case.
    [Suggested by David MARCHALAND]
  * [#27790] ignore omitted tests from 'n% passed' report.
    [Suggested by Daniel Berger]

* 2 minor enchancements
  * [#27832] ignore .git directory. [Suggested by Daniel Berger]
  * [#27792] require 'fileutils' and 'tmpdir' lazily for non-priority
    mode users. [Suggested by David MARCHALAND]

* 2 bug fixes
  * [#27892] modify processed arguments array destructively.
    [Reported by Bob Saveland]
  * work without HOME environment variable.
    [Reported by Champak Ch]

* Thanks
  * David MARCHALAND
  * Daniel Berger
  * Bob Saveland
  * Champak Ch

## 2.0.6 / 2010-01-09

* 3 major enhancements
  * [#27380] Declarative syntax? [Daniel Berger]
    support declarative syntax:

      test "test description in natural language" do
         ...
      end
  * support test description:
      description "test description in natural language"
      def test_my_test
         ...
      end
  * make max diff target string size customizable by
    TEST_UNIT_MAX_DIFF_TARGET_STRING_SIZE environment variable.

* 2 bug fixes
  * [#27374] omit_if unexpected behavior [David MARCHALAND]
  * fix a bug that tests in sub directories aren't load with --basedir.
    [Daniel Berger]

* Thanks
  * David MARCHALAND
  * Daniel Berger

## 2.0.5 / 2009-10-18

* 1 bug fixes
  * [#27314] fix diff may raise an exception. [Erik Hollensbe]

* Thanks
  * Erik Hollensbe

## 2.0.4 / 2009-10-17

* 4 major enhancements
  * use ~/.test-unit.yml as global configuration file.
  * add TAP runner. (--runner tap)
  * support colorized diff:
    http://test-unit.github.io/color-diff.png
  * add Test::Unit::AutoRunner.default_runner= to specify default test runner.

* 4 minor enhancements
  * improve verbose mode output format. (use indent)
  * support `NOT_PASS_THROUGH_EXCEPTIONS`.
  * support arguments option in `#{runner}_options`.
  * TC_ -> Test in sample test case name.

* 1 bug fixes
  * [#27195] test-unit-2.0.3 + ruby-1.9.1 cannot properly test
    DelegateClass subclasses [Mike Pomraning]

* Thanks
  * Mike Pomraning

## 2.0.3 / 2009-07-19

* 6 major enhancements
  * add assert_predicate.
  * add assert_not_predicate.
  * [#24210] assert_kind_of supports an array of classes or modules.
    [Daniel Berger]
  * assert_instance_of supports an array of classes or modules.
  * add --default-priority option.
  * [#26627] add --order option. [Daniel Berger]

* 4 minor enhancements
  * use yellow foreground + black background for error.
  * don't show diff for long string.
  * accept "*term-color" TERM environment as colorizable terminal.
    (e.g. Apple's Terminal)
  * [#26268] add a workaround for test-spec's after_all. [Angelo Lakra]

* 1 bug fix
  * [#23586] re-support ruby 1.9.1. [Diego Pettenò]

* Thanks
  * Diego Pettenò
  * Daniel Berger
  * Angelo Lakra

## 2.0.2 / 2008-12-21

* 2 major enhancements

  * re-support ruby 1.8.5.
  * improve exception object comparison.

* 3 bug fixes

  * [#22723]: collector fails on anonymous classes
  * [#22986]: Test names with '?' blow up on Windows
  * [#22988]: don't create .test-result on non-priority mode.

* Thanks

  * Erik Hollensbe
  * Daniel Berger
  * Bill Lear

## 2.0.1 / 2008-11-09

* 19 major enhancements

  * support ruby 1.9.1.
  * add run_test method to be extensible.
  * improve priority-mode auto off.
  * improve startup/shutdown RDoc. [Daniel Berger]
  * add assert_compare. [#20851] [Designing Patterns]
  * add assert_fail_assertion. [#20851] [Designing Patterns]
  * add assert_raise_message. [#20851] [Designing Patterns]
  * support folded diff.
  * add assert_raise_kind_of. [Daniel Berger]
  * ingore inherited test for nested test case.
  * add assert_const_defined.
  * add assert_not_const_defined.
  * support assert_raise with an exception object.
  * support assert_raise with no arguments that asserts any
    exception is raised. [#22602] [Daniel Berger]
  * support folded dot progress.
  * add --progress-row-max option.
  * support color scheme customize.
  * support configuration file. (YAML)
  * recognize test-XXX.rb files as test files not only test_XXX.rb

* Thanks

  * Daniel Berger
  * Designing Patterns

## 2.0.0 / 2008-06-18

* 15 major enhancements

  * support startup/shutdown. (test case level setup/teardown)
  * support multiple setup/teardown.
  * support pending.
  * support omission.
  * support notification.
  * support colorize.
  * support diff.
  * support test attribute.
  * add assert_boolean.
  * add assert_true.
  * add assert_false.
  * add --priority-mode option.
  * don't use ObjectSpace to collect test cases.
  * make more customizable. (additional options, exception handling and so on)
  * improve Emacs integration.

* 4 major changes

  * remove GTK+1 support.
  * split GTK+ runner as another gem.
  * split FOX runner as another gem.
  * split Tk runner as another gem.

## 1.2.3 / 2008-02-25

* 1 major enhancement

  * Birthday (as a gem)!
