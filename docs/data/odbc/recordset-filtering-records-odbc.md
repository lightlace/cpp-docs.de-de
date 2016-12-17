---
title: "Recordset: Filtern von Datens&#228;tzen (ODBC)"
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
  - "Daten [MFC], Filtern"
  - "Filtern von Recordsets"
  - "Filter [C++], Recordset-Objekt"
  - "ODBC-Recordsets [C++], Filtern von Datensätzen"
  - "Recordsets [C++], Filtern"
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Filtern von Datens&#228;tzen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie ein Recordset so filtern, dass es nur eine bestimmte Untermenge der verfügbaren Datensätze auswählt.  Sie haben z. B. die Möglichkeit, nur die Kursabschnitte für eine bestimmte Vorlesung auszuwählen, etwa MATH101.  Ein Filter ist eine Suchbedingung, die vom Inhalt einer SQL\-**WHERE**\-Klausel definiert wird.  Wenn das Framework den Filter an die SQL\-Anweisung eines Recordsets anhängt, schränkt die **WHERE**\-Klausel die Auswahl ein.  
  
 Sie müssen den Filter eines Recordset\-Objekts einrichten, nachdem Sie das Objekt konstruiert haben, aber noch vor Aufruf seiner **Open**\-Memberfunktion \(oder bevor Sie für ein bereits vorhandenes Recordset\-Objekt, dessen **Open**\-Memberfunktion zuvor aufgerufen wurde, die **Requery**\-Memberfunktion aufrufen\).  
  
#### So geben Sie einen Filter für ein Recordset\-Objekt an  
  
1.  Konstruieren Sie ein neues Recordset\-Objekt oder bereiten Sie ein bereits vorhandenes Recordset\-Objekt für einen **Requery**\-Aufruf vor.  
  
2.  Tragen Sie einen passenden Wert in den [m\_strFilter](../Topic/CRecordset::m_strFilter.md)\-Datenmember des Objekts ein.  
  
     Der Filter ist eine auf NULL abschließende Zeichenfolge, die den Inhalt der SQL\-**WHERE**\-Klausel, jedoch nicht das Schlüsselwort **WHERE** enthält.  Verwenden Sie z. B.  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  In diesem Beispiel wurde die Zeichenfolge "MATH101" in einfache Anführungszeichen eingeschlossen.  In der ODBC\-SQL\-Angabe werden einfache Anführungszeichen dazu verwendet, ein Zeichenfolgenliteral zu kennzeichnen.  Lesen Sie in der Dokumentation des ODBC\-Treibers nach, welche Anführungszeichen das DBMS in diesen Fällen benötigt.  Diese Syntax wird gegen Ende dieses Themas noch genauer beschrieben.  
  
3.  Stellen Sie alle sonstigen benötigten Optionen ein, z. B. die Sortierreihenfolge, das Sperrverhalten und die Parameter.  Die Angabe eines Parameters ist besonders praktisch.  Informationen zur Parametrisierung eines Filters finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
4.  Rufen Sie die **Open**\-Memberfunktion des neuen Objekts auf \(oder **Requery** bei einem bereits vorher geöffneten Objekt\).  
  
> [!TIP]
>  Der Einsatz von Parametern im Filter ist in den meisten Fällen die effizienteste Methode für das Abrufen von Datensätzen.  
  
> [!TIP]
>  Recordsetfilter eignen sich für das [Verknüpfen](../../data/odbc/recordset-performing-a-join-odbc.md) von Tabellen und für den Einsatz von [Parametern](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md), und zwar basierend auf Informationen, die zur Laufzeit abgerufen oder berechnet werden.  
  
 Das Recordset wählt nur die Datensätze aus, die der angegebenen Suchbedingung genügen.  Um z. B. den weiter oben beschriebenen Vorlesungsfilter einzurichten, gehen Sie folgendermaßen vor \(angenommen, die Variable `strCourseID` ist auf einen sinnvollen Wert gesetzt, wie etwa "MATH101"\):  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 Das Recordset enthält Datensätze für alle Kursabschnitte von MATH101.  
  
 Beachten Sie, wie in dem letzten Beispiel die Filterzeichenfolge mithilfe einer Zeichenfolgenvariablen gesetzt wurde.  Diese Methode wird am häufigsten verwendet.  Wenn Sie dagegen den Literalwert 100 für die Vorlesungs\-ID verwenden möchten,  müssen Sie die Filterzeichenfolge folgendermaßen festlegen:  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 Beachten Sie hierbei die Verwendung der einfachen Anführungszeichen. Wenn Sie die Filterzeichenfolge direkt festlegen, dürfen Sie **nicht** schreiben:  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 Diese Verwendung der Anführungszeichen entspricht zwar den ODBC\-Angaben, manche Datenbank\-Management\-Systeme erfordern jedoch möglicherweise andere Anführungszeichen.  Weitere Informationen finden Sie unter [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
> [!NOTE]
>  Wenn Sie die Standard\-SQL\-Zeichenfolge des Recordsets überschreiben, indem Sie eine eigene SQL\-Zeichenfolge an **Open** übergeben, dürfen Sie keinen Filter festlegen, sofern die benutzerdefinierte Zeichenfolge eine **WHERE**\-Klausel enthält.  Weitere Informationen zur Überschreibung von Standard\-SQL finden Sie unter [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Sortieren von Datensätzen \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Recordset: Sperren von Datensätzen \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)