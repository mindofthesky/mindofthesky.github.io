class Solution:

    def fullJustify(self, words: List[str], maxWidth: int) -> List[str]:
        
        _list = [];
        res = [];
        n = 0;
        
        for w in words :
            
            while len(w) + n + len(_list) > maxWidth :
                a = (len(_list) - 1) or 1;
                quque, rem = divmod(maxWidth - n , a);
                for i in range(a) :
                    _list[i] += " " * quque + (" " if i < rem else "");
                res.append("".join(_list));
                n, _list = 0 , [];
                
            _list.append(w);
            n += len(w);
        
        return res + [" ".join(_list).ljust(maxWidth)] if _list else [];
