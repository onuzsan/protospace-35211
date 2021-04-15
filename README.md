
# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false | 
| position   | text   | null: false |

### Association

- has_many :users_prototypes
- has_many :prototypes, through: users_prototypes
- has_many :comments


## prototypes テーブル

| Column     | Type       | Options       |
| ------     | ---------- | ------------- |
| title      | string     | null: false,  |
| catch_copy | text       | null: false,  |
| concept    | text       | null: false,  |
| image      |            |               |
| user       | references |               |

### Association

- has_many :users_prototypes
- has_many :users, through: users_prototypes
- has_many :comments
 

 ## users_prototypes テーブル

| Column     | Type       | Options       |
| ------     | ------     | -----------   |
| users      | references | null: false,  |
| prototypes | references | null: false,  |

### Association

- belongs_to :user
- belongs_to :prototypes


## comments テーブル

| Column    | Type       | Options     |
| ------    | ------     | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |


- belongs_to :users
- belongs_to :prototypes
