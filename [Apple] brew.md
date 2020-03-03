# Brew

## Operation

### Search installed packages
>> brew list

### Search installed services
>> brew services list

### Search packages
>> brew search something

### Install package
>> brew install something
 
### Remove all packages
>> brew list -1 | xargs brew rm

### Run service
>> brew services start service_name

### Show installed packages with tree architecture  
brew deps --tree --installed

# deps           Show dependencies for formula.
# 
#   --list       Show dependencies as a tree. When given
#                multiple formula arguments, show individual
#                trees for each formula. 
#   --installed  List dependencies for formulae that are
#                currently installed. If formula is
#                specified, list only its dependencies that
#                are currently installed.