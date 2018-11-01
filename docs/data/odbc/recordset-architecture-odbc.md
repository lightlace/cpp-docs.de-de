---
title: 'Recordset: Architektur (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: fc44f2b4fcae51cef78d6b660f0cc86ee516e5e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651190"
---
# <a name="recordset-architecture-odbc"></a>Recordset: Architektur (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird beschrieben, die Datenmember, die die Architektur eines Recordset-Objekts enthalten:

- [Felddatenmember](#_core_field_data_members)

- [Parameter-Datenmember](#_core_parameter_data_members)

- [Verwenden von M_nFields und M_nParams-Datenmember](#_core_using_m_nfields_and_m_nparams)

> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn massenzeilenabruf implementiert wird, ähnelt die Architektur. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_a_sample_class"></a> Sample-Klasse

Bei Verwendung der [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** Assistenten, um ein Recordset-Klasse deklarieren, die von abgeleiteten `CRecordset`, die resultierende Klasse verfügt über die allgemeine Struktur dargestellt in der folgenden einfachen Klasse:

```cpp
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

Am Anfang der Klasse, schreibt der Assistent eine Reihe von [Felddatenmember](#_core_field_data_members). Wenn Sie die Klasse erstellen, müssen Sie eine oder mehrere Felddatenmember angeben. Wenn die Klasse parametrisiert wird, wie das Beispiel Klasse ist (mit dem Datenmember `m_strIDParam`), müssen Sie manuell hinzufügen [Parameterdatenmember](#_core_parameter_data_members). Der Assistent unterstützt das Hinzufügen von Parametern für eine Klasse nicht.

##  <a name="_core_field_data_members"></a> Felddatenmember

Die wichtigsten Mitglieder des Recordset-Klasse sind den Felddatenmembern. Für jede Spalte, die Sie aus der Datenquelle auswählen, enthält die Klasse ein Mitglied von Daten für den entsprechenden Datentyp für diese Spalte. Z. B. die [Beispielklasse](#_core_a_sample_class) am Anfang dieses Thema enthält zwei Felddatenmember, beide vom Typ `CString`namens `m_strCourseID` und `m_strCourseTitle`.

Wenn das Recordset eine Gruppe von Datensätzen auswählt, bindet das Framework automatisch die Spalten des aktuellen Datensatzes (nach der `Open` Aufruf, der der erste Datensatz ist aktuell) auf den Felddatenmembern des Objekts. D. h. verwendet das Framework den entsprechenden Felddatenmember als Puffer zum Speichern von den Inhalt der Spalte "Record" ein.

Wenn der Benutzer an einen neuen Datensatz einen Bildlauf durchführt, verwendet das Framework die Felddatenmembern zum Darstellen des aktuellen Datensatzes an. Das Framework aktualisiert die Felddatenmembern, und Ersetzen Sie dabei die Werte des vorherigen Datensatzes. Die Felddatenmember werden auch verwendet, für den aktuellen Datensatz aktualisieren und neue Datensätze hinzufügen. Im Rahmen des Vorgangs zum Aktualisieren eines Datensatzes Geben Sie die Aktualisieren von Werten durch Zuweisen von Werten direkt an den entsprechenden felddatenelement oder Elemente an.

##  <a name="_core_parameter_data_members"></a> Parameter-Datenmember

Wenn die Klasse parametrisiert wird, hat es eine oder mehrere Parameter-Datenmember. Eine parametrisierte Klasse können Sie eine Recordset-Abfrage als Grundlage für Informationen, die abgerufen oder zur Laufzeit berechnet.

In der Regel unterstützt der Parameter die Auswahl, wie im folgenden Beispiel eingrenzen. Auf der Grundlage der [Beispielklasse](#_core_a_sample_class) am Anfang dieses Themas, des Recordset-Objekts möglicherweise die folgende SQL-Anweisung ausgeführt:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?
```

Das "?" ist ein Platzhalter für einen Parameterwert, den Sie zur Laufzeit angeben. Beim Erstellen des Recordsets und legen Sie dessen `m_strIDParam` Datenmember MATH101, SQL-Anweisung für das Recordset wird:

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101
```

Definieren Sie Parameterdatenmember, teilen Sie das Framework über Parameter in der SQL-Zeichenfolge. Das Framework bindet den Parameter, der ODBC wissen, wo Sie die Werte ersetzen für den Platzhalter erhalten kann. In diesem Beispiel enthält das resultierende Recordset nur einen Datensatz der Tabelle "Course" mit einer CourseID-Spalte, deren Wert MATH101 ist. Alle angegebene Spalten für diesen Datensatz ausgewählt sind. Sie können angeben, wie viele Parameter (und Platzhalter) wie erforderlich.

> [!NOTE]
>  MFC nichts selbst mit den Parametern, insbesondere eine Text-Ersetzung wird nicht ausgeführt. Stattdessen teilt MFC ODBC, wo Sie den Parameter erhalten; ODBC ruft die Daten ab und führt die notwendige Parametrisierung.

> [!NOTE]
>  Die Reihenfolge der Parameter ist wichtig. Informationen hierzu und Weitere Informationen zu Parametern finden Sie [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

##  <a name="_core_using_m_nfields_and_m_nparams"></a> Verwenden von M_nFields und m_nParams

Wenn ein Assistent einen Konstruktor für die Klasse schreibt, er initialisiert zudem die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) Datenmember, die angibt, die Anzahl der [Felddatenmember](#_core_field_data_members) in der Klasse. Wenn Sie eine hinzufügen [Parameter](#_core_parameter_data_members) der-Klasse, müssen Sie auch eine Initialisierung für Hinzufügen der [M_nParams](../../mfc/reference/crecordset-class.md#m_nparams) Datenmember, der die Anzahl von Parameterdatenmember angibt. Das Framework verwendet diese Werte mit den Datenelementen zu arbeiten.

Weitere Informationen und Beispiele finden Sie unter [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)