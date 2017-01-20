---
title: "Recordset: Architektur (ODBC)"
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
  - "Felddatenmember"
  - "Felddatenmember, Recordsetarchitektur"
  - "m_nFields-Datenmember"
  - "m_nFields-Datenmember, Recordsets"
  - "m_nParams-Datenmember"
  - "m_nParams-Datenmember, Recordsets"
  - "ODBC-Recordsets, Architektur"
  - "Parameterdatenmember in Recordsets"
  - "Recordsets, Architektur"
  - "Recordsets, Datenmember"
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Architektur (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Dieses Thema beschreibt die Datenmember, aus denen sich die Architektur eines Recordset\-Objekts zusammensetzt:  
  
-   [Felddatenmember](#_core_field_data_members)  
  
-   [Parameterdatenmember](#_core_parameter_data_members)  
  
-   [m\_nFields\-Datenmember und m\_nParams\-Datenmember](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Falls das gesammelte Abrufen von Zeilen implementiert ist, ist die Architektur ähnlich.  Unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) werden die Unterschiede erläutert.  
  
##  <a name="_core_a_sample_class"></a> Beispielklasse  
 Wenn Sie mit dem [MFC\-ODBC\-Consumer\-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) unter **Klasse hinzufügen** eine von `CRecordset` abgeleitete Recordset\-Klasse deklarieren, verfügt die resultierende Klasse über die allgemeine Struktur, die in der folgenden einfachen Klasse dargestellt wird:  
  
```  
class CCourse : public CRecordset  
{  
public:  
   CCourse(CDatabase* pDatabase = NULL);  
   ...  
   CString m_strCourseID;  
   CString m_strCourseTitle;  
   CString m_strIDParam;  
};  
```  
  
 An den Anfang der Klasse schreibt der Assistent einen Satz von [Felddatenmembern](#_core_field_data_members).  Wenn Sie die Klasse erstellen, müssen Sie ein oder mehrere Felddatenmember angeben.  Falls die Klasse parametrisiert ist, wie dies bei der Beispielklasse der Fall ist \(mit dem Datenmember `m_strIDParam`\), müssen Sie [Parameterdatenmember](#_core_parameter_data_members) manuell hinzufügen.  Das Hinzufügen von Parametern zu einer Klasse wird nicht vom Assistenten unterstützt.  
  
##  <a name="_core_field_data_members"></a> Felddatenmember  
 Die wichtigsten Member der Recordset\-Klasse sind die Felddatenmember.  Für jede Spalte, die Sie in der Datenquelle auswählen, enthält die Klasse einen Datenmember des passenden Datentyps für diese Spalte.  Beispielsweise enthält die weiter oben gezeigte [Beispielklasse](#_core_a_sample_class) zwei Felddatenmember vom Typ `CString` mit den Namen `m_strCourseID` und `m_strCourseTitle`.  
  
 Wenn das Recordset eine Gruppe von Datensätzen auswählt, werden die Spalten des aktuellen Datensatzes \(nach dem Aufruf von **Open** ist der erste Datensatz der aktuelle Datensatz\) automatisch vom Framework an die Felddatenmember des Objekts gebunden.  Das Framework setzt den passenden Felddatenmember als Puffer ein, in dem es den Inhalt einer Datensatzspalte speichert.  
  
 Beim Scrollen zu einem neuen Datensatz verwendet das Framework die Felddatenmember, um den aktuellen Datensatz zu repräsentieren.  Das Framework aktualisiert die Felddatenmember, indem es die Werte des vorherigen Datensatzes ersetzt.  Die Felddatenmember werden auch für das Aktualisieren des aktuellen Datensatzes und für das Hinzufügen neuer Datensätze verwendet.  Als Teil des Aktualisierungsprozesses für einen Datensatz geben Sie die aktualisierten Werte an, indem Sie die Werte direkt den entsprechenden Felddatenmembern zuweisen.  
  
##  <a name="_core_parameter_data_members"></a> Parameterdatenmember  
 Eine parametrisierte Klasse verfügt über einen oder mehrere Parameterdatenmember.  Mit einer parametrisierten Klasse können Sie eine Recordset\-Abfrage auf Informationen basieren, die während der Laufzeit abgerufen oder berechnet werden.  
  
 Üblicherweise hilft der Parameter dabei, die Auswahl einzuschränken, wie in dem folgenden Beispiel.  Ausgehend von der [Beispielklasse](#_core_a_sample_class) zu Beginn des Themas könnte das Recordset\-Objekt die folgende SQL\-Anweisung ausführen:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 Das Fragezeichen "?" ist ein Platzhalter für einen Parameterwert, den Sie zur Laufzeit zur Verfügung stellen.  Wenn Sie das Recordset erstellen und für seinen `m_strIDParam`\-Datenmember den Wert MATH101 festlegen, sieht die resultierende SQL\-Anweisung für das Recordset wie folgt aus:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 Durch das Definieren von Parameterdatenmembern informieren Sie das Framework über Parameter innerhalb der SQL\-Zeichenfolge.  Das Framework bindet den Parameter, der ODBC mitteilt, wo sich die an Stelle des Platzhalters einzusetzenden Werte befinden.  In dem Beispiel enthält das resultierende Recordset nur einen Datensatz der Vorlesungstabelle, bei dem die Spalte CourseID den Wert MATH101 aufweist.  Alle angegebenen Spalten dieses Datensatzes sind ausgewählt.  Sie können so viele Parameter \(und Platzhalter\) angeben, wie Sie benötigen.  
  
> [!NOTE]
>  MFC selbst verwendet die Parameter nicht. Insbesondere führt sie damit keine Ersetzung von Text durch.  Vielmehr teilt MFC ODBC mit, wo die Parameterdaten zu finden sind. ODBC ruft die Daten ab und führt die notwendige Parametrisierung aus.  
  
> [!NOTE]
>  Die Reihenfolge der Parameter ist wichtig.  Weitere Informationen zu diesem Thema und Parametern finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a> Verwenden von m\_nFields und m\_nParams  
 Wenn ein Assistent einen Konstruktor für die Klasse schreibt, wird auch der Datenmember [m\_nFields](../Topic/CRecordset::m_nFields.md) initialisiert, der die Anzahl der [Felddatenmember](#_core_field_data_members) der Klasse angibt.  Wenn Sie der Klasse [Parameter](#_core_parameter_data_members) hinzufügen, müssen Sie auch eine Initialisierung für den [m\_nParams](../Topic/CRecordset::m_nParams.md)\-Datenmember hinzufügen, in dem die Anzahl der Parameterdatenmember festgelegt wird.  Das Framework verwendet diese Werte für die Arbeit mit den Datenmembern.  
  
 Weitere Informationen und Beispiele finden Sie unter [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)