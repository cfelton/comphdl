#
# Building a Hello World Chisel without too much sbt/scala/... stuff
#
# sbt looks for default into a folder project/ for build.sdt and Build.scala
# sbt creates per default a target folder

SBT = java -Xmx1024M -Xss8M -XX:MaxPermSize=128M -jar sbt/sbt-launch.jar

# This generates the C++ files by invoking main from
# class HelloMain in package example
# Source directory is configured in project/Build.scala
# Scala/Java build directory is configured in project/Build.scala

# The first two arguments are consumed by sbt, the others are
# forwarded to the 

# command to compile the C++ files is missing

MAIN=error.CombErrMain
MAIN=example.BlinkMain
MAIN=example.FsmMain
MAIN=error.UnusedCErrorMain

all:
	$(SBT) "run-main $(MAIN) --targetDir generated"

test:
	-rm -rf generated
	$(SBT) "run-main $(MAIN) --test --compile --vcd --genHarness --targetDir generated"

# the Verilog version
verilog:
	$(SBT) "run-main $(MAIN) --targetDir generated --backend v"

###### Minimum Makefile ends here ########

intsbt:
	$(SBT)
