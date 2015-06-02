練習問題5.2
関数オブジェクトと一つの数ｎを仮引数とする再帰関数
以下プログラム

def do_n(f, n) :
	if n <= 0 :
		return
	f()
	do_n(f, n-1)

def f() :
	print 'aaa'
	
do_n(f, 5)


練習問題 6.1 比較関数、つまりもしもx > y ならば戻り値は1、x == y ならば、0、x <
y ならば、-1 を返す関数を作成せよ。

def compare(x, y) :
	if x > y :
		return 1
	elif x < y :
		return -1
	else :
		return 0
		
print compare(2, 1)
print compare(1, 2)
print compare(2, 2)



練習問題 6.2 
直角三角形の二辺の長さを引数として受け取り、斜辺の長さを戻り値として返す
関数hypotenuse を段階的な改良法を使って書け。各段階の状況を記録して置くこと。

1.二辺の長さを引数として受け取り、戻り値は不動小数点数であると予測する。

	def hypotenuse(x, y):
		return 0.0

2.二辺の長さの和を求め、斜辺の長さをmath.sqrtを用いて求める。

	def hypotenuse(a,b):
		squared = a**2 + b**2
		print squared
		result = math.sqrt(squared)
		return result

3.最終的に読みやすくなるように不要な文を省く。

	def hypotenuse(a,b):
		squared = a**2 + b**2
		result = math.sqrt(squared)
		return result



練習問題 6.3 
以下の関数 is_between(x, y, z)を書け。ここでx ≦ y ≦ zなら True を返し、
これ以外ならば False を返す。

	def is_between(x, y, z):
		if(x <= y and y <= z):
			return True
		else:
			return False


練習問題7.1 
関数print_nを再帰でなく、繰り返し処理をするプログラムに書き換えよ。

	def print_n(s,n):
		 while n > 0 :
		 	print s
			n = n - 1

	print_n("sho", 5)
	
	実行結果：
	sho
	sho
	sho
	sho
	sho
	


練習問題 7.2 
以上の議論を基に関数square_root を作成せよ。この関数は仮引数として正の数a を持ち、この平方根を求める機能を持つ。平方根はこの関数の戻り値とする。

	def square_root(a) :
		x = a - 1.0
		epsilon = 0.0000001
		while True:
			print x 
			y = (x +  a/x) / 2
			if abs(y-x) < epsilon :
				break
			x = y
		print y
		return y
		
	実行結果：
	3.0
	2.16666666667
	2.00641025641
	2.00001024003
	2.00000000003
	2.0
