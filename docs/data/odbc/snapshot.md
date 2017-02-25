---
title: "Snapshot | Microsoft Docs"
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
  - "Cursorbibliothek [ODBC], Snapshots"
  - "Cursor [ODBC], Statische"
  - "ODBC-Cursorbibliothek [ODBC], Snapshots"
  - "ODBC-Recordsets, Snapshots"
  - "Recordsets, Snapshots"
  - "Snapshots"
  - "Snapshots, Unterstützung in ODBC"
  - "Statische Cursor"
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Snapshot
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Momentaufnahme ist ein Recordset, das eine statische Ansicht von Daten enthält. Momentaufnahmen weisen dabei immer die Werte auf, die sie zu dem Zeitpunkt hatten, als die Momentaufnahme erstellt wurde.  Wenn eine Momentaufnahme geöffnet und alle Datensätze angezeigt wurden, ändern sich weder der Satz der in der Momentaufnahme enthaltenen Datensätze noch deren Werte, bis die Momentaufnahme durch den Aufruf von **Requery** neu erstellt wird.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  Falls anstatt der MFC\-ODBC\-Klassen die MFC\-DAO\-Klassen verwendet werden, lesen Sie die Informationen zu [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md). Dort finden Sie eine Beschreibung der Recordsets vom Typ `Snapshot`.  
  
 Mit Datenbankklassen können aktualisierbare oder schreibgeschützte Momentaufnahmen erstellt werden.  Im Gegensatz zu einem Dynaset spiegelt eine aktualisierbare Momentaufnahme keine Änderungen an Werten von Datensätzen wider, die durch andere Benutzer vorgenommen wurden. Es werden allerdings Aktualisierungen und Löschungen angezeigt, die von Ihrem Programm vorgenommen wurden.  Zu einer Momentaufnahme hinzugefügte Datensätze werden in der Momentaufnahme so lange nicht angezeigt, bis **Requery** aufgerufen wird.  
  
> [!TIP]
>  Eine Momentaufnahme ist ein "statischer Cursor" in ODBC.  Durch statische Cursor können Datenzeilen erst abgerufen werden, wenn zum jeweiligen Datensatz gewechselt wird.  Um sicherzustellen, dass alle Datensätze sofort abgerufen werden, wechseln Sie zum Ende des Recordsets und danach zum ersten anzuzeigenden Datensatz.  Beachten Sie jedoch, dass durch einen Wechsel zum Ende eines Recordsets die Systemleistung herabgesetzt werden kann.  
  
 Momentaufnahmen sind besonders nützlich, wenn Daten bei Operationen wie der Generierung eines Berichts oder der Ausführung von Berechnungen unverändert bleiben sollen.  Da nach einiger Zeit deutliche Unterschiede zwischen der Momentaufnahme und der Datenquelle auftreten können, sollte die Momentaufnahme in regelmäßigen Abständen neu erstellt werden.  
  
 Die Unterstützung für Momentaufnahmen beruht auf der ODBC\-Cursorbibliothek, die die für die Aktualisierungen erforderliche statische Cursor und positionierbare Aktualisierungen für Level 1\-Treiber bereitstellt.  Die Cursorbibliothek\-DLL muss für diese Unterstützung geladen sein.  Wenn ein `CDatabase`\-Objekt konstruiert und die zugehörige `OpenEx`\-Memberfunktion aufgerufen wird, muss die **CDatabase::useCursorLib**\-Option des `dwOptions`\-Parameters angegeben werden.  Durch Aufruf der **Open**\-Memberfunktion wird die Cursorbibliothek standardmäßig geladen.  Wenn statt Momentaufnahmen Dynasets verwendet werden, darf die Cursorbibliothek nicht geladen werden.  
  
 Momentaufnahmen stehen nur dann zur Verfügung, wenn bei der Konstruktion des `CDatabase`\-Objekts die ODBC\-Cursorbibliothek geladen war oder wenn der verwendete ODBC\-Treiber statische Cursor unterstützt.  
  
> [!NOTE]
>  Bei einigen ODBC\-Treibern sind Momentaufnahmen, also statische Cursor, möglicherweise nicht aktualisierbar.  Lesen Sie in der Dokumentation des Treibers nach, welche Cursortypen und Parallelverarbeitungsarten unterstützt werden.  Wenn sichergestellt werden soll, dass Momentaufnahmen aktualisierbar sind, muss vor dem Konstruieren eines `CDatabase`\-Objekts die Cursorbibliothek in den Speicher geladen werden.  Weitere Informationen finden Sie unter [ODBC: Die ODBC\-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Wenn sowohl Momentaufnahmen als auch Dynasets verwendet werden sollen, müssen diese auf zwei verschiedenen `CDatabase`\-Objekten, also zwei unterschiedlichen Verbindungen basieren.  
  
 Weitere Informationen über gemeinsame Eigenschaften von Momentaufnahmen und Recordsets finden Sie unter [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  Weitere Informationen über ODBC*,* Momentaufnahmen und die ODBC\-Cursorbibliothek finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)