# The dtds for my personal use

The `db.dtd` file is the dtd file for database schema, the schema can contain tables and code generate rules.

To use the db.dtd file, can add the following code to schema file.

## Schema Example

```
<?xml version="1.0"?>
<!DOCTYPE db PUBLIC "//swanwish/db" "https://raw.githubusercontent.com/swanwish/dtds/master/db.dtd">
<db name="ot_ownhistory">
  <abstracttable id="base_info">
    <column name="create_time" type="INT" notnull="1" skipupdate="1" json="-" />
    <column name="last_update_time" type="INT" notnull="1" json="lastUpdateTime" />
  </abstracttable>
  <table name="t_profile">
    <column name="profile_id" type="INT" pk="1" autoincrement="1" json="profileId" />
    <column name="profile_name" type="VARCHAR" length="512" notnull="1" json="profileName" />
    <column name="profile_description" type="TEXT" notnull="1" json="profileDescription" />
    <includeabstract id="base_info" />
  </table>
</db>
```