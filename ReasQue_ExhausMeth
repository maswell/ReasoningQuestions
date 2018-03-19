# 方法一：暴力穷举
from collections import Counter
from numpy import *
import datetime
starttime = datetime.datetime.now()
for cout in range(0,4**10):
    # 初始态：10道题目的答案都是 A
    ans = [(cout>>18)%4,(cout>>16)%4,(cout>>14)%4,
           (cout>>12)%4,(cout>>10)%4,(cout>>8 )%4,
           (cout>>6) %4,(cout>>4 )%4,(cout>>2 )%4,cout%4]
    ######## 验证 ########
    # 第二题答案验证debug_pass
    if ans[1] != (ans[4] + 2) % 4:continue
    # 第三题答案验证。与任意一个相同就跳出循环。debug_pass
    if   (ans[2] == 0)&((ans[2] == ans[5])|(ans[2] == ans[1])|(ans[2] == ans[3])):continue
    elif (ans[2] == 1)&((ans[5] == ans[2])|(ans[5] == ans[1])|(ans[5] == ans[3])):continue
    elif (ans[2] == 2)&((ans[1] == ans[2])|(ans[1] == ans[5])|(ans[1] == ans[3])):continue
    elif (ans[2] == 3)&((ans[3] == ans[2])|(ans[3] == ans[5])|(ans[3] == ans[1])):continue
    # 第四题答案验证debug_pass
    if   (ans[3] == 0)&(ans[0] != ans[4]):continue
    elif (ans[3] == 1)&(ans[1] != ans[6]):continue
    elif (ans[3] == 2)&(ans[0] != ans[8]):continue
    elif (ans[3] == 3)&(ans[5] != ans[9]):continue
    # 第五题验证debug_pass
    if   (ans[4] == 0)&(ans[7] != 0):continue
    elif (ans[4] == 1)&(ans[3] != 1):continue
    elif (ans[4] == 2)&(ans[8] != 2):continue
    elif (ans[4] == 3)&(ans[6] != 3):continue
    # 第六题验证debug_pass
    if   (ans[5] == 0)&((ans[7] != ans[1])|(ans[7] != ans[3])):continue
    elif (ans[5] == 1)&((ans[7] != ans[0])|(ans[7] != ans[5])):continue
    elif (ans[5] == 2)&((ans[7] != ans[2])|(ans[7] != ans[9])):continue
    elif (ans[5] == 3)&((ans[7] != ans[4])|(ans[7] != ans[8])):continue
    # 第七题验证，要利用本题答案的唯一性
    ans_min_cut  = Counter(ans).most_common()[-1][0]
    if Counter(ans).most_common()[-1][1] == Counter(ans).most_common()[-2][1]:continue
    if   (ans[6] == 0)&(ans_min_cut != 2) : continue
    elif (ans[6] == 1)&(ans_min_cut != 1) : continue
    elif (ans[6] == 2)&(ans_min_cut != 0) : continue
    elif (ans[6] == 3)&(ans_min_cut != 3) : continue
    # 第八题验证debug_pass
    if   (ans[7] == 0)&(abs(ans[0] - ans[6]) < 2):continue
    elif (ans[7] == 1)&(abs(ans[0] - ans[4]) < 2):continue
    elif (ans[7] == 2)&(abs(ans[0] - ans[1]) < 2):continue
    elif (ans[7] == 3)&(abs(ans[0] - ans[9]) < 2):continue
    # 第九题验证debug_pass
    if   (ans[8] == 0)&(((ans[0]==ans[5])&(ans[4]==ans[5]))|~((ans[0]==ans[5])|(ans[4]==ans[5]))):continue
    elif (ans[8] == 1)&(((ans[0]==ans[5])&(ans[4]==ans[9]))|~((ans[0]==ans[5])|(ans[4]==ans[9]))):continue
    elif (ans[8] == 2)&(((ans[0]==ans[5])&(ans[4]==ans[1]))|~((ans[0]==ans[5])|(ans[4]==ans[1]))):continue
    elif (ans[8] == 3)&(((ans[0]==ans[5])&(ans[4]==ans[8]))|~((ans[0]==ans[5])|(ans[4]==ans[8]))):continue
    # 第十题验证debug_pass
    num_diff = Counter(ans).most_common()[0][1] - Counter(ans).most_common()[-1][1]
    if   (ans[9] == 0)&(num_diff != 3):continue
    elif (ans[9] == 1)&(num_diff != 2):continue
    elif (ans[9] == 2)&(num_diff != 4):continue
    elif (ans[9] == 3)&(num_diff != 1):continue
    ########## 输出 #######
    # 转换为ASCII码
    print('\n',"答案是",'\n')
    answ = ""
    for pri_cut in range(0,10):
        answ = answ + chr(ans[pri_cut] + 65)
    print(answ,'\n')
＃统计计算时间
endtime = datetime.datetime.now()
print (endtime - starttime).seconds
