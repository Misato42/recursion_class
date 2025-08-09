import random
import sys

sys.stdout.buffer.write('最小値を入力してください: '.encode('utf-8'))
sys.stdout.flush()
n = int(sys.stdin.buffer.readline().decode().rstrip('\n'))

sys.stdout.buffer.write('最大値を入力してください: '.encode('utf-8'))
sys.stdout.flush()
m = int(sys.stdin.buffer.readline().decode().rstrip('\n'))

if n > m:
    # エラーメッセージ
    sys.stdout.buffer.write('エラー: 最小値が最大値を超えています\n'.encode('utf-8'))
    sys.stdout.flush()
    exit()

answer = random.randint(n, m)
max_attempts = 5

for attemp in range(1,max_attempts + 1):
    guess = sys.stdout.buffer.write('数字を予測してください'.encode('utf-8'))
    sys.stdout.flush()

    guess_str = sys.stdin.buffer.readline().decode().rstrip('\n')
    guess = int(guess_str)


    if guess == answer:
        sys.stdout.buffer.write('おめでとうございます'.encode('utf-8'))
        sys.stdout.flush()
        break
    else:
        sys.stdout.buffer.write('残念\n'.encode('utf-8'))
        sys.stdout.flush()

