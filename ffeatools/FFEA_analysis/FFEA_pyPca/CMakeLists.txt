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

add_executable(FFEA_convert_traj_to_mdcrd FFEA_convert_traj_to_mdcrd.cpp)

install(TARGETS FFEA_convert_traj_to_mdcrd
        DESTINATION "${PYTHONSTUFF}/FFEA_analysis/FFEA_traj_tools")

# install(TARGETS FFEA_convert_traj_to_mdcrd
#         DESTINATION "${CMAKE_INSTALL_PREFIX}/bin")

install(FILES 
        FFEA_compare_modes.py FFEA_convert_to_PCAsystem.py FFEA_get_PCA_animations.py FFEA_test_projection_convergence.py
        FFEA_get_PCA_eigensystem.py FFEA_get_PCA_projections.py FFEA_test_convergence.py plot_eigensystem_comparison.py
        DESTINATION "${PYTHONSTUFF}/FFEA_analysis/FFEA_pyPca")

