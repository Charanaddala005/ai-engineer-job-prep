python code:
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root is None:
            return None
        root.left, root.right = root.right, root.left
        self.invertTree(root.left)
        self.invertTree(root.right)
        return root

algorithm:
here in this binary tree first we have to do a pre check before getting into the problem i.e, if root is None we have to return None
then we have to invert the values which means value in the left side of the root becomes the value to the right of root 
so we have toswap the values from left to right
and then for the subtrees present to the nodes of the root all we have to do is a recursive function which continues to go on until they reach child node

