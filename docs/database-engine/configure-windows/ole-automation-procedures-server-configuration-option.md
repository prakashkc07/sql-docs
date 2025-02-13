---
title: "Ole Automation Procedures Server Configuration Option"
description: "Learn about the Ole Automation Procedures option. See how it specifies whether SQL Server can instantiate OLE Automation objects within Transact-SQL batches."
author: rwestMSFT
ms.author: randolphwest
ms.date: "03/02/2017"
ms.service: sql
ms.subservice: configuration
ms.topic: conceptual
helpviewer_keywords:
  - "Ole Automation Procedures option"
---
# Ole Automation Procedures Server Configuration Option
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Use the **Ole Automation Procedures** option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches. This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure. For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).  
  
 The **Ole Automation Procedures** option can be set to the following values.  
  
 0  
 OLE Automation Procedures are disabled. Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 1  
 OLE Automation Procedures are enabled.  
  
 When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.  
  
 The current value of the **Ole Automation Procedures** option can be viewed and changed by using the **sp_configure** system stored procedure.  
  
## Examples  
 The following example shows how to view the current setting of OLE Automation procedures.  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 The following example shows how to enable OLE Automation procedures.  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## See Also  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md)   
 [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
  
