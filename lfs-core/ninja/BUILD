####################################################################
#
#
#
####################################################################

####################################################################
# BUILD

#export NINJAJOBS=4

sed -i '/int Guess/a \
  int   j = 0;\
  char* jobs = getenv( "NINJAJOBS" );\
  if ( jobs != NULL ) j = atoi( jobs );\
  if ( j > 0 ) return j;\
' src/ninja.cc

python3 configure.py --bootstrap

#./ninja ninja_test
#./ninja_test --gtest_filter=-SubprocessTest.SetWithLots
