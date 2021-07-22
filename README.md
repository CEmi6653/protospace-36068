# テーブル設計

## users テーブル

| column       | Type        | Options        |
|--------------|-------------|----------------|
|email         | string      | null: false    |
|password      | string      | null: false    |
|name          | string      | null: false    |
|profile       | text        | null: false    |
|occupation    | text        | null: false    |
|position      | text        | null: false    |

### Association
has_many :prototypes #prototypesテーブルとのアソシエーション
has_many :comments #commentsテーブルとのアソシエーション


## prototypes テーブル
| column       | Type        | Options        |
|--------------|-------------|----------------|
| title        | string      | null: false    |
| catch_copy   | text        | null: false    |
| concept      | text        | null: false    |
| user         | references  |


### Association
belong_to :user #usersテーブルとのアソシエーション
has_many :comments #commentテーブルとのアソシエーション



## comments テーブル
| column       | Type        | Options        |
|--------------|-------------|----------------|
| text         | text        | null: false    |
| user         | references  |
| prototype    | references  |

### Association
belongs_to :user #usersテーブルとのアソシエーション
belongs_to :prototype #prototypesテーブルとのアソシエーション

