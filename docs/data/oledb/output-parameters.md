---
title: "Ausgabeparameter"
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
  - "OLE DB, Gespeicherte Prozeduren"
  - "Prozeduraufrufe"
  - "Prozeduraufrufe, Gespeicherte Prozeduren"
  - "Gespeicherte Prozeduren, Aufrufen"
  - "Gespeicherte Prozeduren, Parameter"
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ausgabeparameter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Aufruf einer gespeicherten Prozedur entspricht dem Aufrufen eines SQL\-Befehls.  Der Hauptunterschied besteht darin, dass gespeicherte Prozeduren Ausgabeparameter und Rückgabewerte verwenden.  
  
 In der folgenden gespeicherten Prozedur stellt das erste Fragezeichen \('?'\) den Rückgabewert \(Telefonnummer\) dar; das zweite Fragezeichen ist der Eingabeparameter \(Name\):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Die Eingabe\- und Ausgabeparameter werden in der Parameterzuordnung festgelegt:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Ihre Anwendung muss die von der gespeicherten Prozedur zurückgegebene Ausgabe behandeln.  Die Rückgabe von Ausgabeparametern und Rückgabewerten erfolgt bei verschiedenen OLE DB\-Anbietern zu unterschiedlichen Zeitpunkten während der Ergebnisverarbeitung.  So übermittelt beispielsweise der Microsoft OLE DB\-Anbieter für SQL Server \(SQLOLEDB\) Ausgabeparameter und Rückgabecodes erst, nachdem der Consumer die durch die gespeicherte Prozedur zurückgegebenen Resultsets abgerufen oder abgebrochen hat.  Die Ausgabe wird im letzten TDS\-Paket vom Server zurückgegeben.  
  
## Zeilenanzahl  
 Wenn Sie die OLE DB\-Consumervorlagen zum Ausführen einer gespeicherten Prozedur mit Ausgabeparametern verwenden, wird die Zeilenanzahl erst beim Schließen des Rowsets festgelegt.  
  
 Im folgenden Beispiel gehen wir von einer gespeicherten Prozedur mit einem Rowset und einem Ausgabeparameter aus:  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 Der **@\_rowcount**\-Ausgabeparameter gibt an, wie viele Zeilen tatsächlich aus der Testtabelle zurückgegeben wurden.  In dieser gespeicherten Prozedur ist jedoch die Anzahl der Zeilen auf maximal 50 beschränkt.  Wenn beispielsweise 100 Zeilen getestet würden, betrüge die Zeilenanzahl 50 \(da dieser Code nur die ersten 50 Zeilen abruft\).  Hätte die Tabelle nur 30 Zeilen, betrüge die Zeilenanzahl 30.  Bevor Sie diesen Wert abrufen, müssen Sie **Close** oder **CloseAll** aufrufen, um die Ausgabeparameter auszufüllen.  
  
## Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)