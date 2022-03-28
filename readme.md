# install java-sdk

# install vcstool and  colcon-common-extensions colcon-gradle
python3 -m pip -U install vcstool colcon-common-extensions colcon-gradle

# build fastdds [open x64 native tools command console]

git clone git@github.com:tsungchent/fastdds_repos.git

cd fastdds_repos

vcs import src < fastrtps.repos

colcon build





