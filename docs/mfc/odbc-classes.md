---
title: ODBC-Klassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98ef4509e7e7570d8c07013f0287fe01105e154a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348139"
---
# <a name="odbc-classes"></a>ODBC-Klassen
Diese Klassen können mit der anderen Anwendung Framework-Klassen einfachen Zugriff auf eine Vielzahl von Datenbanken gewähren für die Open Database Connectivity (ODBC)-Treiber zur Verfügung stehen.  
  
 Programme, die ODBC-Datenbanken zugreifen müssen mindestens eine `CDatabase` Objekt und ein `CRecordset` Objekt.  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 Kapselt eine Verbindung mit einer Datenquelle, die über die Sie für die Datenquelle ausgeführt werden können.  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 Kapselt eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt. Recordsets aktivieren Durchführen eines Bildlaufs von Datensatz zu Datensatz, Aktualisieren von Datensätzen (hinzufügen, bearbeiten und Löschen von Datensätzen), qualifizieren die Auswahl mit einem Filter, sortieren die Auswahl, und die Auswahl mit Informationen zu parametrisieren abgerufen oder zur Laufzeit berechnet.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Stellt eine Form anzeigen, die direkt mit einem Recordset-Objekt verbunden. Der Dialogdatenaustausch (DDX) Mechanismus Datenaustausch zwischen des Recordsets und die Steuerelemente der Datensatzansicht angezeigt. Wie alle Formularansichten basieren auf einer Dialogfeldvorlagen-Ressource eine Datensatzansicht. Datensatzansichten unterstützen auch Verschieben von Datensatz zu Datensatz im Recordset, Datensätze aktualisiert werden, und das zugehörigen Recordset schließen, wenn die Datensatzansicht geschlossen wird.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Eine Ausnahme, was bei Auftreten eines in den Datenzugriff Verarbeitung. Diese Klasse dient den gleichen Zweck wie andere Ausnahmeklassen in den Mechanismus zur Ausnahmebehandlung der Klassenbibliothek.  
  
 [CDBException](../mfc/reference/cfieldexchange-class.md)  
 Stellt Kontextinformationen, Datensatzfeldaustausch (RFX), zu unterstützen, die Daten zwischen den Felddatenmembern und Parameterdatenmember von einem Recordset-Objekt und den entsprechenden Tabellenspalten in der Datenquelle austauscht. Analog zu Klasse [CDataExchange](../mfc/reference/cdataexchange-class.md), die auf ähnliche Weise für Dialogdatenaustausch (DDX) verwendet wird.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Kapselt ein Handle für den Speicher für ein binary large Object (BLOB), z. B. eine Bitmap an. `CLongBinary` Objekte werden verwendet, um große Datenmengen-Objekte, die in Datenbanktabellen gespeichert zu verwalten.  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 Können Sie einen Wert zu speichern, ohne befürchten Datentyp des Werts. `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

