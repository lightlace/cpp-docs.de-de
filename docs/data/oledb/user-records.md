---
title: "Benutzerdatens&#228;tze"
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
  - "COLUMN_ENTRY_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Accessoren [C++], Rowsets"
  - "Accessoren [C++], Statische"
  - "BEGIN_ACCESSOR-Makro, Beispiel"
  - "BEGIN_ACCESSOR_MAP-Makro"
  - "CAccessor-Klasse, Beispiel"
  - "COLUMN_ENTRY-Makro"
  - "COLUMN_ENTRY_MAP-Makro"
  - "OLE DB-Consumervorlagen, Benutzerdatensätze"
  - "Rowsets [C++], Accessoren"
  - "Benutzerdatensätze, OLE DB-Consumervorlagen"
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerdatens&#228;tze
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um einen statischen Accessor, also einen aus **CAccessor** abgeleiteten Accessor, verwenden zu können, muss der Consumer über einen Benutzerdatensatz verfügen.  Der Benutzerdatensatz ist eine C\+\+\-Klasse, die Datenelemente zur Behandlung der Ein\- und Ausgabe enthält.  Der ATL OLE DB\-Consumer\-Assistent erstellt einen Benutzerdatensatz für den Consumer.  Sie können dem Benutzerdatensatz Methoden für optionale Aufgaben, z. B. die Behandlung von Befehlen, hinzufügen.  
  
 Der folgende Code zeigt ein Beispiel für einen Benutzerdatensatz, der Befehle behandelt.  Im Benutzerdatensatz repräsentiert `BEGIN_COLUMN_MAP` ein Datenrowset, das dem Consumer von einem Anbieter übergeben wurde.  `BEGIN_PARAM_MAP` stellt einen Satz von Befehlsparametern dar.  In diesem Beispiel wird eine [CCommand](../../data/oledb/ccommand-class.md)\-Klasse zur Behandlung der Befehlsparameter verwendet.  Die Datenmember in den Zuordnungseinträgen stellen Offsets in einem zusammenhängenden Speicherblock für jede Instanz der Klasse dar.  Die `COLUMN_ENTRY`\-Makros entsprechen den `PROVIDER_COLUMN_ENTRY`\-Makros auf der Anbieterseite.  
  
 Weitere Informationen über das **COLUMN\_MAP**\-Makro und das **PARAM\_MAP**\-Makro finden Sie unter [Makros für OLE DB\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## Vom Assistenten generierte Benutzerdatensätze  
 Wenn Sie den ATL\-OLE DB\-Consumer\-Assistenten zum Generieren eines Consumers verwenden, können Sie wahlweise OLE DB\-Vorlagen oder OLE DB\-Attribute verwenden.  Der generierte Code sieht dabei in beiden Fällen unterschiedlich aus.  Informationen zu diesem Code finden Sie unter [Vom Consumer\-Assistenten generierte Klassen](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## Unterstützung für mehrere Accessoren in Benutzerdatensätzen  
 Ausführliche Informationen zu den Szenarien, in denen mehrere Accessoren verwendet werden müssen, finden Sie unter [Verwenden mehrerer Accessoren für ein Rowset](../../data/oledb/using-multiple-accessors-on-a-rowset.md).  
  
 Das folgende Beispiel zeigt den Benutzerdatensatz, der so verändert wurde, dass er mehrere Accessoren im Rowset unterstützt.  Anstelle von `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP` wird für jeden Accessor [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md) und [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) verwendet.  Das `BEGIN_ACCESSOR`\-Makro gibt die Accessornummer \(Offset von 0 \(null\)\) an und bestimmt, ob es sich bei dem Accessor um einen Autoaccessor handelt.  Autoaccessoren rufen `GetData` auf, damit Daten beim Aufruf an [MoveNext](../../data/oledb/crowset-movenext.md) automatisch abgerufen werden.  Bei nicht automatischen Accessoren ist es erforderlich, dass Sie die Daten explizit abrufen.  Verwenden Sie nicht automatische Accessoren, wenn Sie eine Bindung an ein großes Datenfeld \(z. B. ein Bitmapbild\) erstellen, das Sie nicht unbedingt für jeden Datensatz abrufen möchten.  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)