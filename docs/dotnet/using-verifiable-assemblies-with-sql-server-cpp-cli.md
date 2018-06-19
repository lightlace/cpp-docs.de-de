---
title: Verwenden überprüfbarer Assemblys mit SQLServer (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f172eea3108771e129636e9aa95d721d45c99609
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168645"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>Verwenden überprüfbarer Assemblys mit SQL Server (C++/CLI)
Erweiterte gespeicherte Prozeduren, die als Dynamic Link Libraries (DLLs), verpackt bieten eine Möglichkeit zum Erweitern der Funktionalität von SQL Server über Funktionen, die mit Visual C++ entwickelt wurde. Erweiterte gespeicherte Prozeduren werden als Funktionen in DLLs implementiert. Zusätzlich zu den Funktionen, erweiterte gespeicherte Prozeduren können auch definieren [von benutzerdefinierten Typen](../cpp/classes-and-structs-cpp.md) und [Aggregatfunktionen](http://msdn.microsoft.com/en-us/de255454-f45e-4281-81f9-bc61893ac5da) (z. B. SUM oder AVG).  
  
 Wenn ein Client eine erweiterte gespeicherte Prozedur ausgeführt wird, sucht SQL Server für die DLL der erweiterten gespeicherten Prozedur zugeordnet, und lädt diese DLL. SQL Server die angeforderte erweiterte gespeicherte Prozedur aufruft und in einem angegebenen Sicherheitskontext ausgeführt. Die erweiterte gespeicherte Prozedur, und klicken Sie dann übergibt Resultsets und Parameter an den Server zurückgegeben.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] Stellt Erweiterungen in Transact-SQL (T-SQL), die überprüfbare Assemblys in SQL Server installieren können. Der SQL Server-Berechtigungssatz gibt den Sicherheitskontext an, mit der Sicherheit die folgenden Ebenen:  
  
-   Uneingeschränkt: Ausführen von Code auf eigenes Risiko; Code muss nicht überprüfbar typsicher sein.  
  
-   Im abgesicherten Modus: Führen Sie überprüfbar typsicheren Code; mit/clr: safe kompiliert.  
  
 Im Abgesicherter Modus erfordert, dass die ausgeführten Assemblys überprüfbar typsicher sein.  
  
 Erstellen und eine überprüfbare Assembly in SQL Server laden, verwenden Sie die Transact-SQL-Befehle CREATE ASSEMBLY und DROP ASSEMBLY wie folgt:  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 Die PERMISSION_SET-Befehl gibt den Sicherheitskontext und kann die Werte eingeschränkt, SAFE oder erweiterte aufweisen.  
  
 Darüber hinaus können Sie die CREATE FUNCTION-Befehl verwenden, zum Binden an die Namen von Methoden in einer Klasse:  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>Beispiel  
 Die folgende SQL-Skript (z. B. benannte "MyScript.sql"), lädt eine Assembly in SQL Server und stellt eine Methode einer Klasse zur Verfügung:  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 SQL-Skripts können interaktiv in SQL Query Analyzer oder in der Befehlszeile mit dem Hilfsprogramm sqlcmd.exe ausgeführt werden. Die folgende Befehlszeile eine Verbindung mit "EigenerServer", wird die Standarddatenbank verwendet, verwendet eine vertrauenswürdige Verbindung, MyScript.sql Eingaben und Ausgaben MyResult.txt.  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Migrieren zu/CLR: safe (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)