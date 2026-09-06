# Group Anagrams

## Pattern
Hash Map + Sorting

## Algorithm

The main idea is to use the sorted version of each string as a key in a hash map.

1. First, create an empty hash map called `groups`.

2. Go through each string in the given array one by one.

3. For every string, sort its characters and convert the sorted characters back into a string.

   For example:
   - `"eat"` → `"aet"`
   - `"tea"` → `"aet"`
   - `"ate"` → `"aet"`
   - `"tan"` → `"ant"`

4. The sorted string is used as the key because all anagrams will produce the same sorted string.

5. Check whether the key already exists in the hash map.
   - If the key already exists, add the current string to the list stored under that key.
   - If the key does not exist, create a new list with the current string.

6. After going through all the strings, return all the values of the hash map because each value represents one group of anagrams.

## Example

Input:

["eat", "tea", "tan", "ate", "nat", "bat"]

After sorting each string:

"eat" → "aet"
"tea" → "aet"
"tan" → "ant"
"ate" → "aet"
"nat" → "ant"
"bat" → "abt"

The hash map will look like:

{
    "aet": ["eat", "tea", "ate"],
    "ant": ["tan", "nat"],
    "abt": ["bat"]
}

Finally, we return the values of the hash map.

## Code

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:

        groups = {}

        for s in strs:
            key = "".join(sorted(s))

            if key in groups:
                groups[key].append(s)
            else:
                groups[key] = [s]

        return list(groups.values())
