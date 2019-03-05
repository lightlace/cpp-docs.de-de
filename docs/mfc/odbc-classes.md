---
title: ODBC-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: 75e022ea3e5de4a57f0ef2b1e3f312654c2889ec
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267133"
---
# <a name="odbc-classes"></a>ODBC-Klassen

Diese Klassen funktionieren mit der anderen Anwendung Framework-Klassen einfachen Zugriff auf eine Vielzahl von Datenbanken zu gewähren, für die Open Database Connectivity (ODBC)-Treiber zur Verfügung stehen.

Programme, die ODBC-Datenbanken verwenden müssen mindestens einen `CDatabase` Objekt und ein `CRecordset` Objekt.

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
Kapselt eine Verbindung mit einer Datenquelle, die über die Sie für die Datenquelle ausgeführt werden können.

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
Kapselt einen Satz von Datensätzen aus einer Datenquelle ausgewählt. Durch Recordsets aktivieren, Durchführen eines Bildlaufs von Datensatz zu Datensatz, Aktualisieren von Datensätzen (hinzufügen, bearbeiten und Löschen von Datensätzen), qualifizieren die Auswahl mit einem Filter, sortieren die Auswahl, und parametrisieren die Auswahl mit den Informationen abgerufen oder zur Laufzeit berechnet.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt verbunden. Die Dialogdatenaustausch (DDX)-Mechanismus eine Übertragung von Daten zwischen dem Recordset und der Steuerelemente der Datensatzansicht angezeigt. Wie alle Formularansichten ist eine Dialogfeldvorlagen-Ressource eine Datensatzansicht abhängig. Datensatzansichten unterstützen auch das Verschieben von Datensatz zu Datensatz im Recordset, Aktualisieren von Datensätzen und das zugehörigen Recordset schließen, wenn die Datensatzansicht geschlossen wird.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Eine Ausnahme aus Fehlern beim Datenzugriff Verarbeitung. Diese Klasse dient demselben Zweck wie die anderen Ausnahmeklassen in der Mechanismus für die Ausnahmebehandlung der Klassenbibliothek.

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
Stellt Kontextinformationen für den Datensatzfeldaustausch (RFX), zu unterstützen, die Daten zwischen den Felddatenmembern und Parameterdatenmember von einem Recordset-Objekt und den entsprechenden Spalten in der Datenquelle austauscht. Analog zu Klasse [CDataExchange](../mfc/reference/cdataexchange-class.md), die auf ähnliche Weise für Dialogdatenaustausch (DDX) verwendet wird.

## <a name="related-classes"></a>Verwandte Klassen

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Kapselt ein Handle für den Speicher für ein binary large Object (BLOB), z. B. eine Bitmap. `CLongBinary` Objekte werden verwendet, zum Verwalten von große Datenobjekte, die in Datenbanktabellen gespeichert.

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
ermöglicht es Ihnen, einen Wert zu speichern, ohne sich Gedanken über den Datentyp des Werts zu. `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
