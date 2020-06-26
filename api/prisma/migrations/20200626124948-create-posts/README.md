# Migration `20200626124948-create-posts`

This migration has been generated at 6/26/2020, 12:49:48 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
PRAGMA foreign_keys=OFF;

CREATE TABLE "quaint"."Post" (
"body" TEXT NOT NULL  ,"createdAt" DATE NOT NULL DEFAULT CURRENT_TIMESTAMP ,"id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,"title" TEXT NOT NULL  )

PRAGMA foreign_keys=off;
DROP TABLE "quaint"."UserExample";;
PRAGMA foreign_keys=on

PRAGMA "quaint".foreign_key_check;

PRAGMA foreign_keys=ON;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200626123742-create-post..20200626124948-create-posts
--- datamodel.dml
+++ datamodel.dml
@@ -1,18 +1,16 @@
 datasource DS {
   provider = "sqlite"
-  url = "***"
+  url = "***"
 }
 generator client {
   provider      = "prisma-client-js"
   binaryTargets = env("BINARY_TARGET")
 }
-// Define your own datamodels here and run `yarn redwood db save` to create
-// migrations for them.
-// TODO: Please remove the following example:
-model UserExample {
-  id    Int     @id @default(autoincrement())
-  email String  @unique
-  name  String?
+model Post {
+  id        Int      @id @default(autoincrement())
+  title     String
+  body      String
+  createdAt DateTime @default(now())
 }
```


