# Sahrul_btg_00MM

# Combination generator for a given geohash at the next level
def getCombinations(string):
def get_combinations(string):
    base32 = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'j', 'k', 'm',
              'n', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
    return [string + '{0}'.format(i) for i in base32]
@@ -28,9 +28,8 @@ def compress(geohashes, minlevel, maxlevel):
    final_geohashes_size = 0

    # Input size less than 32
    if len(geohashes) < 32:
        puts(colored.red(
            'Need a minimum of 32 geohashes to compress! Could read only ' + str(len(geohashes)) + '!\n'))
    if len(geohashes) == 0:
        puts(colored.red('No geohashes found!\n'))
        return False


@@ -52,7 +51,7 @@ def compress(geohashes, minlevel, maxlevel):
                if part not in deletegh and geohash not in deletegh:

                    # Generate combinations
                    combinations = set(getCombinations(part))
                    combinations = set(get_combinations(part))

                    # If all generated combinations exist in the input set
                    if combinations.issubset(geohashes):
                    
