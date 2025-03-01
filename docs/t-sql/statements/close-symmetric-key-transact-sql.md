---
description: "CLOSE SYMMETRIC KEY (Transact-SQL)"
title: "CLOSE SYMMETRIC KEY (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "05/15/2017"
ms.prod: sql
ms.prod_service: "database-engine, sql-database"
ms.reviewer: ""
ms.technology: t-sql
ms.topic: reference
f1_keywords: 
  - "CLOSE SYMMETRIC KEY"
  - "CLOSE_SYMMETRIC_KEY_TSQL"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "closing symmetric keys"
  - "encryption [SQL Server], symmetric keys"
  - "symmetric keys [SQL Server], closing"
  - "CLOSE SYMMETRIC KEY statement"
  - "cryptography [SQL Server], symmetric keys"
ms.assetid: 3b083cbb-3c6a-4f59-8d34-601db1efcc83
author: VanMSFT
ms.author: vanto
monikerRange: "= azuresqldb-current || = azuresqldb-mi-current || >= sql-server-2016 || >= sql-server-linux-2017||= azure-sqldw-latest"
---
# CLOSE SYMMETRIC KEY (Transact-SQL)
[!INCLUDE [sql-asdb-asa](../../includes/applies-to-version/sql-asdb-asa.md)]

  Closes a symmetric key, or closes all symmetric keys open in the current session.  
  
  ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md) 

> [!NOTE]
> [!INCLUDE[synapse-analytics-od-unsupported-syntax](../../includes/synapse-analytics-od-unsupported-syntax.md)]
  
## Syntax  
  
```syntaxsql
CLOSE { SYMMETRIC KEY key_name | ALL SYMMETRIC KEYS }  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## Arguments
 *Key_name*  
 Is the name of the symmetric key to be closed.  
  
## Remarks  
 Open symmetric keys are bound to the session not to the security context. An open key will continue to be available until it is either explicitly closed or the session is terminated. CLOSE ALL SYMMETRIC KEYS will close any database master key that was opened in the current session by using the [OPEN MASTER KEY](../../t-sql/statements/open-master-key-transact-sql.md) statement.  Information about open keys is visible in the [sys.openkeys &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-openkeys-transact-sql.md) catalog view.  
  
## Permissions  
 No explicit permission is required to close a symmetric key.  
  
## Examples  
  
### A. Closing a symmetric key  
 The following example closes the symmetric key `ShippingSymKey04`.  
  
```sql  
CLOSE SYMMETRIC KEY ShippingSymKey04;  
GO  
```  
  
### B. Closing all symmetric keys  
 The following example closes all symmetric keys that are open in the current session, and also the explicitly opened database master key.  
  
```sql  
CLOSE ALL SYMMETRIC KEYS;  
GO  
```  
  
## See Also  
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [ALTER SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/alter-symmetric-key-transact-sql.md)   
 [OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/open-symmetric-key-transact-sql.md)   
 [DROP SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-symmetric-key-transact-sql.md)  
  
  
