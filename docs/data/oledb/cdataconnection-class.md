---
title: "CDataConnection-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataConnection"
  - "ATL.CDataConnection"
  - "CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection-Klasse"
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Verbindung mit der Datenquelle.  
  
## Syntax  
  
```  
class CDataConnection  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Konstruktor.  Instanziiert und initialisiert ein `CDataConnection`\-Objekt.|  
|[Kopieren](../../data/oledb/cdataconnection-copy.md)|Erstellt eine Kopie einer Verbindung der vorhandenen Daten.|  
|[Öffnen](../../data/oledb/cdataconnection-open.md)|Öffnet eine Verbindung zu einer Datenquelle mithilfe einer festgelegten Initialisierungszeichenfolge.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Öffnet eine neue Sitzung auf der aktuellen Verbindung.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)|Bestimmt, ob die aktuelle Sitzung oder nicht geöffnet ist.|  
|[Operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Bestimmt, ob die aktuelle Sitzung oder nicht geöffnet ist.|  
|[Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Gibt einen Verweis auf das enthaltende `CDataSource`\-Objekt zurück.|  
|[Operator CDataSource\*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|Gibt einen Zeiger an das übergeordnete `CDataSource`\-Objekt zurück.|  
|[Operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|Gibt einen Verweis auf das enthaltende `CSession`\-Objekt zurück.|  
|[Operator CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)|Gibt einen Zeiger an das übergeordnete `CSession`\-Objekt zurück.|  
  
## Hinweise  
 `CDataConnection` ist eine wichtige Klasse zum Erstellen von Clients, da sie die erforderlichen Objekte \(Sitzung und Datenquelle\) und zur Arbeit kapselt, die Sie, bei der Verbindung mit einer Datenquelle ausführen müssen  
  
 Ohne `CDataConnection` müssen Sie ein `CDataSource`\-Objekt erstellen, ihre [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)\-Methode aufrufen, dann, eine Instanz eines [CSession](../../data/oledb/csession-class.md)\-Objekts zu erstellen, die [Öffnen](../../data/oledb/csession-open.md)\-Methode aufrufen, dann [CCommand](../../data/oledb/ccommand-class.md), ein Objekt erstellt und sein **Öffnen** aufrufen \* Methoden.  
  
 Mit `CDataConnection` müssen Sie lediglich ein Verbindungsobjekt erstellen, führen es eine Initialisierungszeichenfolge, verwenden diese Verbindung an geöffneten Befehlen.  Wenn Sie auf die Verbindung zur Datenbank wiederholt verwenden planen, empfiehlt es sich, die Verbindung geöffnet bleibt, und `CDataConnection` stellt eine einfache Möglichkeit, das verwendet.  
  
> [!NOTE]
>  Wenn Sie einer Datenbankanwendung erstellen, die mehrere Sitzungen behandeln muss, müssen Sie [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md) verwenden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)