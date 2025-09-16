# 林竣翔

## 關於我
- **Python 程式開發**  
- 網頁前端設計 (HTML / CSS / JS)  
- 資料庫管理 (MySQL / Firebase)
- 炒幣
- DOGE coin必須要去1u

_「持續學習，讓今天的自己比昨天更好。」_

[我最喜歡的網站 - 派網](https://www.pionex.com/zh-TW/signUp?r=AtQxewvS)
### 都給我快去註冊

![風景圖](https://picsum.photos/600/300)

> 「成功不是終點，失敗也不是末日，最重要的是繼續前進的勇氣。」 — 丘吉爾

## 教育與經歷

| 時間 | 經歷 |
|------|------|
| 2020-2023 | 高雄市立三民家商 資料處理科 |
| 2023-2027 | 國立高雄科技大學 資訊管理系 |

## 程式碼示範 (PHP)
```php
<?php
class Database {
    private $pdo;

    public function __construct($host, $db, $user, $pass) {
        try {
            $this->pdo = new PDO("mysql:host=$host;dbname=$db", $user, $pass);
            $this->pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
            echo "✅ 資料庫連線成功\n";
        } catch (PDOException $e) {
            die("❌ 資料庫連線失敗: " . $e->getMessage());
        }
    }

    public function getUsers() {
        $stmt = $this->pdo->query("SELECT id, name, email FROM users LIMIT 5");
        return $stmt->fetchAll(PDO::FETCH_ASSOC);
    }
}


$db = new Database("localhost", "testdb", "root", "password");
$users = $db->getUsers();
foreach ($users as $user) {
    echo $user['id'] . " - " . $user['name'] . " (" . $user['email'] . ")\n";
}
?>
