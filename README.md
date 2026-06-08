# week2Day1
leetcode
#questions 1
class Solution {
    public boolean isAnagram(String s, String t) {
        Map<Character, Integer> count = new HashMap<>();
        for (char x : s.toCharArray()) {
            count.put(x, count.getOrDefault(x, 0) + 1);
        }
    
        for (char x : t.toCharArray()) {
            count.put(x, count.getOrDefault(x, 0) - 1);
        }
        
        for (int val : count.values()) {
            if (val != 0) {
                return false;
            }
        }
        
        return true;
    }
}
#question 2
class Solution {
    public int firstUniqChar(String s) {
        char st[]=s.toCharArray();
      HashMap<Character,Integer>map=new HashMap<>();
      for(char c:st){
        map.put(c,map.getOrDefault(c,0)+1);
      }
        for (int i = 0; i < st.length; i++) {
            if (map.get(st[i]) == 1) {
                return i;
            }
        }
        return -1;
    }
}
#question 3
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        HashMap<Character, Integer> frq = new HashMap<>();
        for (int i = 0; i < magazine.length(); i++) {
            char ch = magazine.charAt(i);
            frq.put(ch, frq.getOrDefault(ch, 0) + 1);
        }
        for (int i = 0; i < ransomNote.length(); i++) {
            char ch = ransomNote.charAt(i);

            if (frq.getOrDefault(ch, 0) == 0) {
                return false;
            }

            frq.put(ch, frq.get(ch) - 1);
        }

        return true;
    }
}


