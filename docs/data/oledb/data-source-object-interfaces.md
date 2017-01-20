---
title: "Datenquellenobjekt-Schnittstellen"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Datenquellenobjekte [C++]"
  - "Datenquellenobjekte [C++], Schnittstellen"
  - "Schnittstellen [C++], Liste"
  - "Schnittstellen [C++], OLE DB"
  - "OLE DB [C++], Schnittstellen"
  - "OLE DB-Anbietervorlagen [C++], Objektschnittstelle"
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Datenquellenobjekt-Schnittstellen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle sind die erforderlichen und optionalen Schnittstellen aufgeführt, die in OLE DB für Datenquellenobjekte definiert sind.  
  
|Schnittstelle|Erforderlich?|Durch OLE DB\-Vorlagen implementiert?|  
|-------------------|-------------------|-------------------------------------------|  
|`IDBCreateSession`|Erforderlich|ja|  
|`IDBInitialize`|Erforderlich|ja|  
|`IDBProperties`|Erforderlich|ja|  
|[\<caps:sentence id\="tgt14" sentenceid\="731a3344bc1c6b5f8f54d9de3524f18a" class\="tgtSentence"\>IPersist\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Erforderlich|ja|  
|[\<caps:sentence id\="tgt17" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|nein|  
|`IDBDataSourceAdmin`|Optional|nein|  
|`IDBInfo`|Optional|nein|  
|[\<caps:sentence id\="tgt26" sentenceid\="7e6a12ecd4cb3b1bd45dccf9421ed567" class\="tgtSentence"\>IPersistFile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|nein|  
|`ISupportErrorInfo`|Optional|nein|  
  
 Das Datenquellenobjekt implementiert die Schnittstellen `IDBProperties`, `IDBInitialize` und `IDBCreateSession` durch Vererbung.  Es können zusätzliche Funktionen unterstützt werden, je nachdem, ob Sie die Vererbung von einer dieser Implementierungsklassen zulassen oder nicht.  Wenn Sie die `IDBDataSourceAdmin`\-Schnittstelle unterstützen möchten, müssen Sie die `IDBDataSourceAdminImpl`\-Klasse erben.  
  
## Siehe auch  
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)