# 
#  This file is part of the FFEA simulation package
#  
#  Copyright (c) by the Theory and Development FFEA teams,
#  as they appear in the README.md file. 
# 
#  FFEA is free software: you can redistribute it and/or modify
#  it under the terms of the GNU General Public License as published by
#  the Free Software Foundation, either version 3 of the License, or
#  (at your option) any later version.
# 
#  FFEA is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
# 
#  You should have received a copy of the GNU General Public License
#  along with FFEA.  If not, see <http://www.gnu.org/licenses/>.
# 
#  To help us fund FFEA development, we humbly ask that you cite 
#  the research papers on the package.
#


add_test(NAME precomp COMMAND ${PROJECT_BINARY_DIR}/src/ffea sphere_63_120_two.ffea)
set_tests_properties(precomp PROPERTIES ENVIRONMENT OMP_NUM_THREADS=1)

add_test(NAME precomp_PBC COMMAND ${PROJECT_BINARY_DIR}/src/ffea sphere_63_120_two-PBC.ffea)
set_tests_properties(precomp_PBC PROPERTIES ENVIRONMENT OMP_NUM_THREADS=1 DEPENDS precomp)

add_test(NAME precomp_check_both COMMAND ${PYTHON_EXECUTABLE} check.py)
set_tests_properties(precomp_check_both PROPERTIES DEPENDS precomp_PBC)




