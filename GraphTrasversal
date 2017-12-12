import java.util.*; 
import java.util.Stack ;

/**
 *
 * @author 16==2D 
 * @version 1
 */
public class GraphTrasversal
{
    private static Timer t=new Timer();
    public static void main(String [] args){
        boolean [][] a={{true, true,true,false},{true, true,true, true},{true,true,true,true},{true,true,true,true}};
        DFS(a);
        BFS(a);
        
    }
    public static void BFS (boolean[][]k){
        Queue<Integer> q = new PriorityQueue<Integer>();
        int [] pr= new int[k[1].length];
        int i=0;
        int index=0;
        t.startTimer();
        do{
            if(q.peek()==null){
                System.out.println(i+1);
                pr[index]=i;
                index++;
            }
            else{//&& !inArray(pr, i)
                i=q.poll();
                //System.out.println(i+1);
                //pr[index]=j;
                //index++; commet out bottom if this code is used ok boiiiii
            }
            for(int j=0;j<k.length;j++){
                if (k[j][i]&& i!=j&& !inArray(pr, j)){//vertex connected to self with edge eqaul to wieght of zero
                    q.add(j);
                    System.out.println(j+1);
                    pr[index]=j;
                    index++;
                    k[j][i]=false;
                    k[i][j]=false;//dont have to check and add to queue so it dosent hhave to be printed again since it was already printed
                }
            }
        }while(q.peek()!=null && index<k[1].length);
        t.endTimer();
        System.out.println(t.getTimeInPreciseSeconds());
        t.resetTimer();
    }
    public static void DFS(boolean[][]k){
        Stack<Integer> s= new Stack<Integer>();
        int [] pr=new int[k[1].length];
        int i=0;
        int index=0;
        t.startTimer();
        do{
            if (s.empty()){
                System.out.println(i+1);
                pr[index]=i;
                index++;
            }
            else{
                i=s.peek();
                s.pop();
            }
            for (int j=0;j<k.length;j++){
                if (k[j][i] && i!=j && !inArray(pr, j)){
                    s.push(j);
                    System.out.println(j+1);
                    pr[index]=j;
                    index++;
                    k[j][i]=false;
                    k[i][j]=false;
                }
            }
        
        }while(s.empty() && k[1].length==pr.length);
        t.endTimer();
        System.out.println(t.getTimeInPreciseSeconds());
        t.resetTimer();
    }
    public static boolean inArray(int []k, int r){
        for (int i=0; i<k.length;i++){
            if (k[i]==r) return true;
        }
        return false;
    }
   
}

