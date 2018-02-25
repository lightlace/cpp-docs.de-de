---
title: Benutzerdatensatz | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbb073aceaff855de700eae6d8aede148f9b8bcc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="user-record"></a>Benutzerdatensatz
Benutzerdatensatz enthält den Code und die Struktur, die die Spaltendaten für ein Rowset darstellt. Ein Benutzerdatensatz kann zur Kompilierzeit oder zur Laufzeit erstellt werden. Wenn Sie einen Anbieter mithilfe der ATL-OLE DB-Anbieter-Assistenten erstellen, erstellt der Assistent einen Standard-Benutzerdatensatz, der wie folgt aussieht (vorausgesetzt, dass Sie einen Anbieternamen [kurzer Name] "MyProvider" angegeben):  
  
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
  
 Der OLE DB-Anbietervorlagen werden alle OLE DB-spezifischen Aspekte in Bezug auf die Clientinteraktionen abgedeckt. Zum Abrufen der Spaltendaten benötigt, die auf eine Antwort der Anbieter Ruft die `GetColumnInfo` -Funktion, die Sie im Benutzerdatensatz platzieren müssen. Sie können explizit überschreiben `GetColumnInfo` im Benutzerdatensatz, z. B. durch Deklarieren sie in der .h-Datei wie hier gezeigt:  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Das entspricht:  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Sie müssen auch implementieren `GetColumnInfo` in der Benutzerdatensatz cpp-Datei.  
  
 Die Makro-Makros zu unterstützen, bei der Erstellung einer `GetColumnInfo` Funktion:  
  
-   BEGIN_PROVIDER_COLUMN_MAP definiert, der Funktionsprototyp und einen statischen Array von **ATLCOLUMNINFO-Struktur** Strukturen.  
  
-   PROVIDER_COLUMN_ENTRY definiert und initialisiert ein einzelnes **ATLCOLUMNINFO-Struktur**.  
  
-   END_PROVIDER_COLUMN_MAP schließt das Array und die Funktion. Es wird auch die Anzahl der Arrayelemente in das `pcCols` Parameter.  
  
 Wenn ein Benutzerdatensatz zur Laufzeit erstellt wird **GetColumnInfo** verwendet die `pThis` Parameter um einen Zeiger auf eine Instanz von Rowset- oder zu empfangen. Befehle und Rowsets unterstützen, müssen die `IColumnsInfo` Schnittstelle, damit Informationen in der Spalte, die aus dieser Zeiger abgerufen werden kann.  
  
 **CommandClass** und **RowsetClass** sind die Befehls- und Rowsetobjekte, die den Benutzerdatensatz zu verwenden.  
  
 Ein ausführlicheres Beispiel zum Überschreiben von `GetColumnInfo` in einem Benutzerdatensatz finden Sie unter [Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)