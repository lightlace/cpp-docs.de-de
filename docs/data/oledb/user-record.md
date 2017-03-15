---
title: "Benutzerdatensatz | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Benutzerdatensatz"
  - "Datensätze, Benutzer"
  - "Rowsets, Benutzerdatensatz"
  - "Benutzerdatensätze"
  - "Benutzerdatensätze, Beschreibung"
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Benutzerdatensatz
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch den Benutzerdatensatz wird Code und die Datenstruktur bereitgestellt, die die Spaltendaten für ein Rowset darstellt.  Ein Benutzerdatensatz kann zur Kompilierungs\- oder zur Laufzeit erstellt werden.  Wenn Sie einen Anbieter mit dem ATL\-OLE DB\-Anbieter\-Assistenten erstellen, generiert der Assistent einen mit dem folgenden Beispiel vergleichbaren Standardbenutzerdatensatz \(es wird davon ausgegangen, dass Sie einen Anbieternamen \[kurzer Name\] für "MyProvider" angegeben haben\):  
  
```  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 Durch die OLE DB\-Anbietervorlagen werden alle OLE DB\-spezifischen Aspekte in Bezug auf die Clientinteraktionen abgedeckt.  Um die für eine Antwort benötigten Spaltendaten zu erhalten, ruft der Anbieter die `GetColumnInfo`\-Funktion auf, die Sie in den Benutzerdatensatz einfügen müssen.  Sie können `GetColumnInfo` im Benutzerdatensatz durch die im Folgenden dargestellte Deklaration in der H\-Datei explizit überschreiben:  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Dies ist identisch mit:  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Zusätzlich muss `GetColumnInfo` in der CPP\-Datei des Benutzerdatensatzes implementiert werden.  
  
 Die **PROVIDER\_COLUMN\_MAP**\-Makros bieten Unterstützung beim Erstellen einer `GetColumnInfo`\-Funktion:  
  
-   Durch **BEGIN\_PROVIDER\_COLUMN\_MAP** werden der Funktionsprototyp und ein statisches Array mit **ATLCOLUMNINFO**\-Strukturen definiert.  
  
-   Durch `PROVIDER_COLUMN_ENTRY` wird eine einzelne **ATLCOLUMNINFO**\-Struktur definiert und initialisiert.  
  
-   Durch **END\_PROVIDER\_COLUMN\_MAP** werden das Array und die Funktion geschlossen.  Zusätzlich wird die Anzahl der Arrayelemente in den `pcCols`\-Parameter eingefügt.  
  
 Wenn ein Benutzerdatensatz zur Laufzeit erstellt wird, verwendet **GetColumnInfo** den `pThis`\-Parameter, um einen Zeiger auf ein Rowset oder auf eine Befehlsinstanz zu erhalten.  Befehle und Rowsets müssen die `IColumnsInfo`\-Schnittstelle unterstützen, sodass über diesen Zeiger Spalteninformationen abgerufen werden können.  
  
 **CommandClass** und **RowsetClass** entsprechen dem Befehl und dem Rowset, der bzw. das den Benutzerdatensatz verwendet.  
  
 Ein ausführliches Beispiel dazu, wie `GetColumnInfo` in einem Benutzerdatensatz überschrieben wird, finden Sie unter [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## Siehe auch  
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)