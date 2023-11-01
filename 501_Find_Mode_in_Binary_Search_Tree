from collections import defaultdict

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class Solution:
    def findMode(self, root: TreeNode):
        def inorder(node):
            nonlocal max_count
            nonlocal mode

            if not node:
                return

            inorder(node.left)

            count_dict[node.val] += 1
            if count_dict[node.val] > max_count:
                max_count = count_dict[node.val]
                mode = [node.val]
            elif count_dict[node.val] == max_count:
                mode.append(node.val)

            inorder(node.right)

        if not root:
            return []

        max_count = 0
        mode = []
        count_dict = defaultdict(int)

        inorder(root)

        return mode
