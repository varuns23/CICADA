CICADA standalone algo pattern testing

1) Tests are to be executed from krieger machine which sits behind UW login gateway

ssh login.hep.wisc.edu
ssh krieger

2) Copy the content of directory below to your area. The directory contains tools, 
scripts and reference test vectors.

cp -R /afs/hep.wisc.edu/home/asvetek/public/CICADA_algo_standalone_testing/* <MY_DIR>

3) Move to where you copied the directory from step 2 and execute a script below to confirm 
that CTP7 CICADA card is ready for testing. If you see any deviation from the reference output
shown below, please reach out. Input test vectors that are used for these reference tests were
provided previously by Pallabi.

source algo_reference_test.sh


-- Reference run ---

$ source algo_reference_test.sh
Executing  101_test ... SUCCESS (output pattern match).
Executing  102_test ... SUCCESS (output pattern match).
Executing  103_test ... SUCCESS (output pattern match).
Executing  104_test ... SUCCESS (output pattern match).
Executing  105_test ... SUCCESS (output pattern match).
Executing  106_test ... SUCCESS (output pattern match).
Executing  107_test ... SUCCESS (output pattern match).
Executing  108_test ... SUCCESS (output pattern match).
Executing  109_test ... SUCCESS (output pattern match).
Executing  110_test ... SUCCESS (output pattern match).

---------------------

The entire script takes roughly 1 minute to execute.

4) Now you can proceed with your pattern tests. Copy your input test vector(s) to
"data" subdirectory from where the tools will pick it up. Output test vectors will
also be written to "data" subdirectory.

Use "pattern_test.sh" script for testing.

Here's an example run:

$ source pattern_test.sh 101_test/Regions_match.txt output.txt

Output test vector for this run can be found at data/output.txt
