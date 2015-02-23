public class Solution {
    public String minWindow(String S, String T) {
        if(S==null||T==null) return null;
        
        Map<Character, Integer> map=new HashMap<Character, Integer>();
        int lenT=T.length();
        int lenS=S.length();
        
        for(int i=0;i<lenT;i++){
            Integer times=map.get(T.charAt(i));
            if(times==null){
                map.put(T.charAt(i), 1);
            }else{
                map.put(T.charAt(i), times+1);
            }
        }
        
        int left=0;
        int right=0;
        int size=0;
        int minLen = Integer.MAX_VALUE;
        String ret="";
        
        for(;right<lenS;right++){
            char tmp=S.charAt(right);
           
            if(map.containsKey(tmp)){
                map.put(tmp, map.get(tmp)-1);
                if(map.get(tmp)==0){
                    size++;
                }
            }
            
            while(left<lenS){
                char c=S.charAt(left);
                if(map.get(c)!=null&&map.get(c)>=0){
                    break;
                }
                if(map.get(c)!=null){
                    map.put(c, map.get(c)+1);
                }
                left++;
            }
        
            int len=right-left+1;
            if(size==map.size()&&len<minLen){
                ret=S.substring(left,right+1);
                minLen=len;
            }
        }
        
        return ret;
    }
}
