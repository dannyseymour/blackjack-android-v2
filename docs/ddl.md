## Data Definition Language for data model

```sql
CREATE TABLE IF NOT EXISTS Card (`card_id` INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, `created` INTEGER NOT NULL, `hand_id` INTEGER NOT NULL, `rank` TEXT NOT NULL, `suit` TEXT NOT NULL, FOREIGN KEY(`hand_id`) REFERENCES `Hand`(`hand_id`) ON UPDATE NO ACTION ON DELETE CASCADE );
CREATE INDEX IF NOT EXISTS `index_Card_created` ON `${TABLE_NAME}` (`created`);
CREATE INDEX IF NOT EXISTS `index_Card_hand_id` ON `${TABLE_NAME}` (`hand_id`);
CREATE TABLE IF NOT EXISTS Card (`hand_id` INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, `created` INTEGER NOT NULL, `updated` INTEGER NOT NULL, `dealer` INTEGER NOT NULL, `round_id` INTEGER NOT NULL, `wager` INTEGER NOT NULL, `outcome` TEXT, FOREIGN KEY(`round_id`) REFERENCES `Round`(`round_id`) ON UPDATE NO ACTION ON DELETE CASCADE );
CREATE INDEX IF NOT EXISTS `index_Hand_created` ON `${TABLE_NAME}` (`created`);
CREATE INDEX IF NOT EXISTS `index_Hand_updated` ON `${TABLE_NAME}` (`updated`);
CREATE INDEX IF NOT EXISTS `index_Hand_round_id` ON `${TABLE_NAME}` (`round_id`);  
```

[`ddl.sql`](ddl.sql)