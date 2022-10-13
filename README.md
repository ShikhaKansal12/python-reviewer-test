// Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.
//

class Solution {
    public boolean isIsomorphic(String s, String t) {
        
       if(s.length() != t.length())
           return false;
        
     return transformString(s).equals(transformString(t)) ;
    }
    
    private String transformString(String s)
    {
        Map<Character, Integer> map = new HashMap<>();
        StringBuilder st = new StringBuilder();
        
        for(int i = 0; i< s.length(); i++)
        {
            char c = s.charAt(i);
            
            if(!map.containsKey(c))
                map.put(c,i);
            
            st.append(Integer.toString(map.get(c)));
            st.append(" ");
        }
        
        return st.toString();
    }
}
