---
title: "Verwenden &#252;berpr&#252;fbarer Assemblys mit SQL Server (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Überprüfbare Assemblys [C++], Mit SQL Server"
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden &#252;berpr&#252;fbarer Assemblys mit SQL Server (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Dynamic Link Libraries \(DLLs\) gepackte, erweiterte gespeicherte Prozeduren bieten eine Möglichkeit, SQL Server\-Funktionalität durch Funktionen zu erweitern, die mit [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] entwickelt wurden.  Erweiterte gespeicherte Prozeduren werden in DLLs als Funktionen implementiert.  Neben Funktionen können erweiterte gespeicherte Prozeduren auch [benutzerdefinierte Typen](../cpp/classes-and-structs-cpp.md) und [Aggregatfunktionen](assetId:///de255454-f45e-4281-81f9-bc61893ac5da) \(z. B. SUM oder AVG\) definieren.  
  
 Wenn ein Client eine erweiterte gespeicherte Prozedur ausführt, sucht SQL Server nach der DLL, die mit der erweiterten gespeicherten Prozedur verknüpft ist, und lädt diese DLL.  Die angeforderte erweiterte gespeicherte Prozedur wird durch SQL Server aufgerufen und in einem vorgegebenen Sicherheitskontext ausgeführt.  Die erweiterte gespeicherte Prozedur übergibt dann Ergebnisse und gibt Parameter an den Server zurück.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] stellt Erweiterungen für Transact\-SQL \(T\-SQL\) zur Verfügung, damit Sie in SQL Server überprüfbare Assemblys installieren können.  Der SQL Server\-Berechtigungssatz gibt über die folgenden Sicherheitsebenen den Sicherheitskontext an:  
  
-   Uneingeschränkter Modus: Führen Sie den Code auf eigene Gefahr aus. Der Code ist unter Umständen nicht nachweisbar typsicher.  
  
-   Abgesicherter Modus: Führen Sie nachweisbar typsicheren, mit \/clr:safe kompilierten Code aus.  
  
 Für den abgesicherten Modus müssen die ausgeführten Assemblys nachweisbar typsicher sein.  
  
 Um eine überprüfbare Assembly zu erstellen und in SQL Server zu laden, verwenden Sie die Transact\-SQL\-Befehle CREATE ASSEMBLY und DROP ASSEMBLY wie folgt:  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 Der Befehl PERMISSION\_SET gibt den Sicherheitskontext an und kann die Werte UNRESTRICTED, SAFE oder EXTENDED erhalten.  
  
 Außerdem können Sie den Befehl CREATE FUNCTION verwenden, um in einer Klasse an Methodennamen zu binden:  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## Beispiel  
 Das folgende SQL\-Skript \(z. B. "MyScript.sql"\) lädt eine Assembly in SQL Server und stellt eine Methode einer Klasse zur Verfügung:  
  
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
  
 SQL\-Skripts können interaktiv in SQL Query Analyzer oder über die Befehlszeilenoption mit dem Dienstprogramm sqlcmd.exe ausgeführt werden.  Durch die folgende Befehlszeile wird eine Verbindung zu MyServer hergestellt, und mithilfe der Standarddatenbank und einer vertrauenswürdigen Verbindung wird MyScript.sql eingegeben und MyResult.txt ausgegeben.  
  
```  
sqlcmd –S MyServer -E –i myScript.sql –o myResult.txt  
```  
  
## Siehe auch  
 [Gewusst wie: Migrieren auf \/clr:safe](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)