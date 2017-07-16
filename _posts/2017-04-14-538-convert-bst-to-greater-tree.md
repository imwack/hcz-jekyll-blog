---
layout: post
title: "538. Convert BST to Greater Tree"
date: 2017-04-14 20:16
author: imwack
comments: true
categories: [LeetCode]
tags: []
---
<div class="question-info text-info">


*   Given a Binary Search Tree (BST), convert it to a Greater Tree such that every key of the original BST is changed to the original key plus sum of all keys greater than the original key in BST.
</div>
<div class="question-content">

**Example:**


**Input:** The root of a Binary Search Tree like this:
                  5
                /   \
               2     13
    
    **Output:** The root of a Greater Tree like this:
                 18
                /   \
              20     13</pre>
    <div>
    
    **Solution: 先遍历右孩子 然后根节点  然后左孩子 dfs...**
    <pre class="pure-highlightjs"><code class="">class Solution {
    public:
        void dfs(TreeNode *root,int &amp;sum){
            if(root==NULL) return ;
    
            if(root-&gt;right) dfs(root-&gt;right,sum);
    
                root-&gt;val+=sum;
                sum = root-&gt;val;
    
            if(root-&gt;left) dfs(root-&gt;left,sum);
        }
        TreeNode* convertBST(TreeNode* root) {
            int sum=0;
            dfs(root,sum);
            return root;
        }
    };`

&nbsp;

&nbsp;

</div>
</div>
