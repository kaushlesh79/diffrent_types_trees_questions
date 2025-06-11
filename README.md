### diffrent_types_trees_questions



## 1. Root to leaf path Probelems 
 # quetion : Smallest String Starting From Leaf (Medium) [988 leetcode] 
 ```bash 
              // trees ---> root to leaf path problems
      
       // similar to diffrent paths approach 
      
      class Solution {
      public:
      
          vector<string>res;
         
         void lexo_small_path(TreeNode*root , string ans){  // dfs for going root to leaf in all path
      
          if(root==NULL) return ;
      
          ans+=(root->val+'a');   // root->val+'a'  === converting integer to char 
      
          if(!root->left && !root->right){  // when reach to leaf 
      
              reverse(ans.begin() , ans.end()); // leaf to root path is reverse of normal path(root to leaf )
              res.push_back(ans);
              return ;
          }
      
           lexo_small_path(root->left , ans);
           lexo_small_path(root->right , ans);
         }
      
      
      
          string smallestFromLeaf(TreeNode* root) {
      
          string ans="";
      
           lexo_small_path(root , ans);
      
      
           sort(res.begin() , res.end());
      
           return *res.begin();
      
      
              
          }
      };
```

## 2. Ancestor Problems 




