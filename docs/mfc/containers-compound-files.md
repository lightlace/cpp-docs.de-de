---
title: 'Container: Verbunddateien | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8983fd8cb51a9f305ef4b0fad4d546fc8091f5a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348344"
---
# <a name="containers-compound-files"></a>Container: Verbunddateien
Dieser Artikel beschreibt die Komponenten und die Implementierung der Verbunddateien sowie die vor- und Nachteile der Verwendung von Verbunddateien in den OLE-Anwendungen.  
  
 Verbunddateien sind ein wesentlicher Bestandteil des OLE. Sie werden verwendet, um die Datenübertragung und OLE-dokumentspeicherung zu vereinfachen. Verbunddateien sind eine Implementierung des Modells Active strukturierten Speicher. Konsistente Schnittstellen vorhanden, die Unterstützung für die Serialisierung ein Speicherkonto, einen Stream oder ein Objekt "Datei". Verbunddateien werden durch die Klassen in der Microsoft Foundation Class-Bibliothek unterstützt `COleStreamFile` und `COleDocument`.  
  
> [!NOTE]
>  Mithilfe einer Verbunddatei bedeutet nicht, dass die Informationen von einem OLE-Dokument oder ein Verbunddokument stammen. Verbunddateien sind nur eine dieser Methoden Verbunddokumente OLE-Dokumente und andere Daten zu speichern.  
  
##  <a name="_core_components_of_a_compound_file"></a> Komponenten einer Verbunddatei  
 Die OLE-Implementierung von Verbunddateien verwendet drei Objekttypen: Streamobjekte, Speicherobjekte und `ILockBytes` Objekte. Diese Objekte ähneln die Bestandteile einer Standarddateisystem auf folgende Weise:  
  
-   Streamobjekte, z. B. Dateien, Speichern von Daten eines beliebigen Typs.  
  
-   Speicherobjekte wie Verzeichnisse, können andere Speicherkonto und Stream-Objekte enthalten.  
  
-   **LockBytes** Objekte darstellen, die Schnittstelle zwischen den Speicherobjekten und die physische Hardware. Sie bestimmen, wie die tatsächlichen Bytes auf beliebigen Geräten Speicher geschrieben werden die **LockBytes** Objekt zugegriffen wird, z. B. ein Festplattenlaufwerk oder ein Bereich des globalen Arbeitsspeicher. Weitere Informationen zu **LockBytes** Objekte und die `ILockBytes` Schnittstelle, finden Sie unter der *OLE Programmer's Reference*.  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Vor- und Nachteile der Verbunddateien  
 Verbunddateien bieten Vorteile, die nicht verfügbar, mit früheren Methoden der Dateispeicher. Dazu zählen:  
  
-   Inkrementelle Datei zugreifen zu können.  
  
-   Zugriffsmodi-Datei.  
  
-   Die Standardisierung der Dateistruktur.  
  
 Den möglichen Nachteilen der Verbunddateien – größere Leistung und des Umfangs Probleme im Zusammenhang mit der Speicher auf Disketten – sollten werden berücksichtigten When entscheiden, ob sie in Ihrer Anwendung verwenden.  
  
###  <a name="_core_incremental_access_to_files"></a> Inkrementelle Zugriff auf Dateien  
 Inkrementelle Zugriff auf Dateien ist eine automatische Vorteil der Verwendung von Verbunddateien. Da es sich bei eine Verbunddatei als "Dateisystem in einer Datei" angezeigt werden kann, können einzelne Objekttypen, z. B. Stream oder Speicher, ohne die Notwendigkeit, laden die gesamte Datei zugegriffen werden. Dies kann sich die Zeit verringern, die eine Anwendung für den Zugriff auf neue Objekte für die Bearbeitung durch den Benutzer muss. Inkrementelle Aktualisierung, basierend auf dasselbe Konzept, ähnliche Vorteile bietet. Statt die gesamte Datei nur zum Speichern der Änderungen auf ein Objekt speichern Speichert OLE nur das Stream oder Speicher-Objekt, die vom Benutzer bearbeitet.  
  
###  <a name="_core_file_access_modes"></a> Zugriffsmodi für Datei  
 Bestimmen, wann Änderungen an Objekten in einer Verbunddatei auf den Datenträger ein Commit ausgeführt werden können, ist ein weiterer Vorteil der Verwendung von Verbunddateien. Der Modus, in dem Dateien, entweder transaktiven oder direct zugegriffen werden, bestimmt, wann Änderungen ein Commit ausgeführt werden.  
  
-   Transaktionsmodus verwendet einen Zweiphasen-Commit-Vorgang um nehmen Änderungen an Objekten in einer Verbunddatei, wodurch sowohl der alte als auch die neue Kopien des Dokuments verfügbar beibehalten, bis der Benutzer entscheidet, speichern oder die Änderungen rückgängig machen.  
  
-   Direkten Modus umfasst Änderungen auf das Dokument an, wie sie festgelegt wurden, ohne die Möglichkeit, die sie später rückgängig machen.  
  
 Weitere Informationen zu Zugriffsmodi, finden Sie unter der *OLE Programmer's Reference*.  
  
###  <a name="_core_standardization"></a> Standardisierung  
 Die standardisierte Struktur Verbunddateien ermöglicht andere OLE-serveranwendungen durchsuchen Verbunddateien, die von der OLE-Anwendung ohne Kenntnisse der Anwendung, die tatsächlich, die Datei erstellt erstellt.  
  
###  <a name="_core_size_and_performance_considerations"></a> Größe und Leistungsaspekte  
 Wegen der Komplexität der Speicherstruktur Verbunddatei sowie die Möglichkeit zum Speichern von Daten inkrementell, Dateien, die mit diesem Format größer sein als andere Dateien tendenziell unstrukturierten oder "Flatfileformat" Speicher. Wenn Ihre Anwendung häufig lädt und speichert die Dateien, können Verbunddateien die Dateigröße wesentlich schneller als Verbunddateien erhöhen Benutzung. Da Verbunddateien große abrufen können, können die Zugriffszeit für Dateien auf gespeichert und daraus Disketten geladen ebenfalls betroffen sein resultierende verzögerten Zugriff auf Dateien.  
  
 Ein anderes Problem, das auf die Leistung auswirkt, ist Compound-Fragmentierung. Die Größe einer Verbunddatei richtet sich nach den Unterschieden zwischen den vor- und Nachnamen Festplattensektoren von der Datei verwendet. Eine fragmentierte Datei kann viele Bereiche des freien Speicherplatzes enthalten, die Daten enthalten, jedoch werden gezählt, wenn die Berechnung der Größe. Diese Bereiche werden während der Lebensdauer einer Verbunddatei durch das Einfügen oder Löschen von Speicherobjekten erstellt.  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> Mithilfe von Verbunddateiformats für Ihre Daten  
 Nach dem erfolgreichen Erstellen einer Anwendung, die eine Dokumentklasse abgeleitet wurde `COleDocument`, stellen Sie sicher, dass Ihre Hauptspeicherorte für Dokumentkonstruktor ruft `EnableCompoundFile`. Wenn der Anwendungs-Assistent OLE-containeranwendungen erstellt, ist dieser Aufruf automatisch eingefügt.  
  
 In der *OLE Programmer's Reference*, finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034), [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015), und [ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238).  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)   
 [COleStreamFile-Klasse](../mfc/reference/colestreamfile-class.md)   
 [COleDocument-Klasse](../mfc/reference/coledocument-class.md)
