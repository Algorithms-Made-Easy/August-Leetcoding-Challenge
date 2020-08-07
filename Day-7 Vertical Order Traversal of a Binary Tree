/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    List<Location> locations=null;
    public List<List<Integer>> verticalTraversal(TreeNode root) {
        
        List<List<Integer>> result=new ArrayList<>();
        locations=new ArrayList<>();
        dfs(root,0,0);
        Collections.sort(locations);
        int x=locations.get(0).x;
        result.add(new ArrayList<>());
        
        for(Location l: locations){
            if(x!=l.x){
                x=l.x;
                result.add(new ArrayList<>());
            }
            result.get(result.size()-1).add(l.val);
        }
        return result;
    }
    
    private void dfs(TreeNode root,int x,int y){
        if(root!=null){
            locations.add(new Location(x,y,root.val));
            dfs(root.left,x-1,y-1);
            dfs(root.right,x+1,y-1);
        }
    }
    
    class Location implements Comparable<Location>{
        int x,y,val;
        
        Location(int x,int y,int val){
            this.x=x;
            this.y=y;
            this.val=val;
        }
        
        @Override
        public int compareTo(Location l){
            if(this.x!=l.x){
            return Integer.compare(this.x,l.x);
            }
            if(this.y!=l.y){
                return Integer.compare(l.y, this.y);
            }
            else {
                return Integer.compare(this.val,l.val);
            }
        }
    }
}
