# install vcstool and  colcon-common-extensions
 python3 -m pip -U install vcstool colcon-common-extensions

# import repos
git clone git@github.com:tsungchent/fastdds_repos.git
cd fastdds_repos
vcs import src < fastrtps.repos
colcon build
