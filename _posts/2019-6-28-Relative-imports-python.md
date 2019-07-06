---
layout: post
title: Relative imports in python
---

Có 2 cách để load một file python :
1. load như một module 
2. load như một file thực thi

Khi thực hiện câu lệnh python myfile.py thì fie sẽ được load như một file thực thi (top-level script).
python -m myfile sẽ load như một module. Trường hợp này cũng tương tự như khi ta import một file từ file thực thi khác.
Khi một file được load vào bộ nhớ, nó sẽ được gán một tên. Nếu file đó load dưới dạng thực thi trực tiếp (top-level script) nó sẽ có tên là __main__. Nếu ta load dưới dạng module, file sẽ có tên dạng package.filename.
Ví dụ 

	
	package/
		__init__.py
		a/
			__init__.py
			a1.py
		b/
			__init__.py
			b1.py
		moduleX.py

Khi ta chaỵ câu lệnh `python a1.py` trong thư mục `a/`, các thành phần của `a1.py` sẽ được load dưới tên `__main__` , muốn import các thành phần từ moduleX.py sẽ không được.

Khi  đó muốn import moduleX từ a1.py sẽ cần chạy ở thư mục package.

`python a/a1.py`

[nguồn](https://stackoverflow.com/questions/14132789/relative-imports-for-the-billionth-time/14132912#14132912)
