---
title: 'Recordset: Architektur (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets, data members
- field data members, recordset architecture
- field data members
- m_nParams data member, recordsets
- recordsets, architecture
- parameter data members in recordsets
- m_nFields data member
- ODBC recordsets, architecture
- m_nParams data member
- m_nFields data member, recordsets
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 169d371327137cf4f51ed10429eb5e9708a0e088
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-architecture-odbc"></a>Recordset: Architektur (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Dieses Thema beschreibt die Datenmember, aus die die Architektur von einem Recordset-Objekt besteht:  
  
-   [Felddatenmember](#_core_field_data_members)  
  
-   [Parameterdatenmember](#_core_parameter_data_members)  
  
-   [Verwenden von M_nFields und M_nParams-Datenmember](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn gesammelte implementiert wird, gleicht die Architektur. Um die Unterschiede zu verstehen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_a_sample_class"></a>Beispiel für eine Klasse  
 Bei Verwendung der [MFC-ODBC-Consumer-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** Assistenten, um eine Recordsetklasse Deklarieren von abgeleiteten `CRecordset`, die resultierende Klasse verfügt über die allgemeine Struktur, die in der folgenden einfachen angezeigt Klasse:  
  
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
  
 Am Anfang der Klasse schreibt der Assistent eine Reihe von [Felddatenmember](#_core_field_data_members). Wenn Sie die Klasse erstellen, müssen Sie eine oder mehrere Felddatenmember angeben. Wenn die Klasse parametrisiert ist, wie das Beispiel Klasse ist (mit dem Datenmember `m_strIDParam`), müssen Sie manuell hinzufügen [Parameterdatenmember](#_core_parameter_data_members). Der Assistent zum unterstützt Hinzufügen von Parametern zu einer Klasse nicht.  
  
##  <a name="_core_field_data_members"></a>Felddatenmember  
 Die wichtigsten Elemente der Recordset-Klasse sind den Felddatenmembern. Für jede Spalte, die Sie aus der Datenquelle auswählen, enthält die Klasse einen Datenmember des entsprechenden Datentyps für diese Spalte. Z. B. die [Beispielklasse](#_core_a_sample_class) gezeigt am Anfang dieses Thema enthält zwei Felddatenmember des Typs `CString`namens `m_strCourseID` und `m_strCourseTitle`.  
  
 Wenn das Recordset eine Gruppe von Datensätzen auswählt, bindet das Framework automatisch die Spalten des aktuellen Datensatzes (nach der **öffnen** Aufruf, der erste Datensatz aktuell ist) den Felddatenmembern des Objekts. D. h. verwendet das Framework das entsprechende felddatenelement als Puffer, in dem der Inhalt einer Spalte Datensatz gespeichert.  
  
 Wenn der Benutzer zu einem neuen Datensatz einen Bildlauf durchführt, verwendet das Framework die Felddatenmembern zum aktuellen Datensatz darstellen. Das Framework aktualisiert die Felddatenmembern Werte des vorherigen Datensatzes ersetzen. Die Felddatenmember werden auch zum Aktualisieren des aktuellen Datensatzes sowie zum Hinzufügen neuer Datensätze verwendet. Im Rahmen des Vorgangs zum Aktualisieren eines Datensatzes Geben Sie das Aktualisieren von Werten durch Zuweisen von Werten direkt in das entsprechende Felddatenmember oder die Elemente an.  
  
##  <a name="_core_parameter_data_members"></a>Parameterdatenmember  
 Wenn die Klasse parametrisiert ist, muss es sich um eine oder mehrere Parameterdatenmember. Eine parametrisierte Klasse können Sie die Informationen zur Laufzeit abgerufen oder berechnet eine Recordset-Abfrage basieren.  
  
 Der Parameter in der Regel hilft, schränken Sie die Auswahl, wie im folgenden Beispiel. Auf der Grundlage der [Beispielklasse](#_core_a_sample_class) am Anfang dieses Themas, u. u. das Recordset-Objekt die folgende SQL-Anweisung ausgeführt:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 Das "?" ist ein Platzhalter für einen Parameterwert, den Sie zur Laufzeit angeben. Bei der Erstellung des Recordsets und legen Sie dessen `m_strIDParam` Datenmember MATH101, SQL-Anweisung für das Recordset wird:  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 Durch die Definition Parameterdatenmember, informieren Sie das Framework über Parameter in der SQL-Zeichenfolge. Das Framework bindet den Parameter, der ODBC wissen, wo Sie die Werte als Ersatz für den Platzhalter abrufen kann. Im Beispiel enthält das resultierende Recordset nur einen Datensatz in die Course-Tabelle mit einer CourseID-Spalte, deren Wert MATH101 ist. Alle angegebene Spalten dieses Datensatzes werden ausgewählt. Sie können angeben, wie viele Parameter (und Platzhalter) wie erforderlich.  
  
> [!NOTE]
>  MFC führt keine Aktion selbst mit den Parametern – insbesondere eine Ersetzung von Text wird nicht ausgeführt. Stattdessen teilt MFC ODBC mit, wo Sie den Parameter erhalten; ODBC ruft die Daten ab und führt die notwendige Parametrisierung.  
  
> [!NOTE]
>  Die Reihenfolge der Parameter ist wichtig. Informationen über diese und Weitere Informationen zu Parametern finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a>Verwenden von M_nFields und m_nParams  

 Wenn ein Assistent einen Konstruktor für die Klasse schreibt, initialisiert es auch die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) -Datenmember, der angibt, die Anzahl der [Felddatenmember](#_core_field_data_members) in der Klasse. Wenn Sie jeden hinzufügen [Parameter](#_core_parameter_data_members) zur-Klasse, müssen Sie auch eine Initialisierung für Hinzufügen der [M_nParams](../../mfc/reference/crecordset-class.md#m_nparams) Datenmember, die die Anzahl der Parameterdatenmember angibt. Das Framework verwendet diese Werte zur Bearbeitung der Datenmember.  
  
 Weitere Informationen und Beispiele finden Sie unter [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)