---
title: 'Container: Verbunddateien | Microsoft-Dokumentation'
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
ms.openlocfilehash: 956a53587feb63706b824c502b46b09698f991be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433035"
---
# <a name="containers-compound-files"></a>Container: Verbunddateien

Dieser Artikel beschreibt die Komponenten und die Implementierung der compound-Dateien und deren vor- und Nachteile der Verwendung in Ihren Anwendungen OLE-compound-Dateien.

Compound-Dateien sind ein wesentlicher Bestandteil OLE. Sie werden verwendet, um die Datenübertragung und OLE-Dokumentspeicher zu vereinfachen. Compound-Dateien sind eine Implementierung des Modells Active strukturierten Speicher. Konsistente Schnittstellen Verbunddateien ein Speicherkonto, einen Stream oder ein Dateiobjekt. Compound-Dateien werden in der Microsoft Foundation Class-Bibliothek von Klassen unterstützt `COleStreamFile` und `COleDocument`.

> [!NOTE]
>  Verwenden einer Verbunddatei bedeutet nicht, dass die Informationen von einem OLE-dienstdokument oder einem Verbunddokument stammt. Compound-Dateien stellen lediglich eine der Möglichkeiten zum Speichern von zusammengesetzten Dokumenten, OLE-Dokumente und andere Daten.

##  <a name="_core_components_of_a_compound_file"></a> Komponenten einer Verbunddatei

Die OLE-Implementierung von Verbunddateien verwendet drei Objekttypen: Streamobjekte, Speicherobjekte und `ILockBytes` Objekte. Diese Objekte sind ähnlich wie die Komponenten von einer standard-Dateisystem auf folgende Weise:

- Stream-Objekte, z. B. Dateien, speichern Daten eines beliebigen Typs.

- Storage-Objekte, z. B. Verzeichnisse können andere Speicherkonto und Stream-Objekten enthalten.

- `LockBytes` Objekte repräsentieren die Schnittstelle zwischen dem Storage-Objekte und die physische Hardware. Sie bestimmen, wie die tatsächlichen Bytes geschrieben werden, auf ein Speichergerät die `LockBytes` -Objekt zugegriffen wird, z. B. eine Festplatte oder einen Teil der globalen Arbeitsspeicher. Weitere Informationen zu `LockBytes` Objekte und die `ILockBytes` Schnittstelle, finden Sie unter den *OLE-Programmierreferenz*.

##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> Vor- und Nachteile von Verbunddateien

Compound-Dateien bieten Vorteile, die nicht verfügbar, mit früheren Methoden von File Storage. Dazu zählen:

- Inkrementelle Datei zugreifen zu können.

- Zugriffsmodi für die Datei.

- Die Standardisierung der Struktur der Datei.

Den möglichen Nachteilen der Verbunddateien – große Netzwerkgröße und-Leistung-Probleme im Zusammenhang mit Speicher auf Disketten – sollten werden als bei entscheiden, ob Sie sie in Ihrer Anwendung verwenden.

###  <a name="_core_incremental_access_to_files"></a> Inkrementelle Zugriff auf Dateien

Inkrementelle Zugriff auf Dateien ist ein automatischer Vorteil der Verwendung von compound-Dateien. Da es sich bei eine Verbunddatei als eine "File System in einer Datei" angezeigt werden kann, können einzelne Objekttypen, z. B. Stream oder Speicher, ohne dass die gesamte Datei laden zugegriffen werden. Dies kann die Zeit erheblich verringern, die eine Anwendung den Zugriff auf neue Objekte für die Bearbeitung durch den Benutzer muss. Inkrementelle Aktualisierung, basierend auf dem gleichen Konzept, ähnliche Vorteile bietet. Statt die gesamte Datei zu speichern Sie die Änderungen an einem Objekt speichern Speichert OLE nur das Stream oder Speicher-Objekt, die vom Benutzer bearbeitet.

###  <a name="_core_file_access_modes"></a> Zugriffsmodi für Datei

Um zu bestimmen, wann Änderungen an Objekten in einer Verbunddatei auf den Datenträger ein Commit ausgeführt werden können, ist ein weiterer Vorteil der Verwendung von Verbunddateien. Der Modus, in dem Dateien, entweder transaktiven oder direkte zugegriffen werden, bestimmt, wann Änderungen ein Commit ausgeführt werden.

- Transaktiven Modus verwendet einen Zweiphasen-Commit-Vorgang, um nehmen Änderungen an Objekten in einer Verbunddatei, bleibt dabei sowohl der alte als auch die neuen Kopien des Dokuments zur Verfügung, bis der Benutzer entscheidet, die entweder gespeichert oder die Änderungen rückgängig machen.

- Direkten Modus umfasst Änderungen am Dokument an, wie sie ohne die Möglichkeit, die später rückgängig gemacht werden.

Weitere Informationen zu Access-Modi finden Sie unter den *OLE-Programmierreferenz*.

###  <a name="_core_standardization"></a> Standardisierung

Die standardisierte Struktur von Verbunddateien kann andere OLE-Anwendungen durchsuchen, compound-Dateien erstellt, die von der OLE-Anwendung ohne Kenntnis der Anwendung, die tatsächlich die Datei erstellt.

###  <a name="_core_size_and_performance_considerations"></a> Größe und Überlegungen zur Leistung

Aufgrund der Komplexität der Speicherstruktur Verbunddatei sowie die Möglichkeit zum Speichern von Daten inkrementell, Dateien, die mit diesem Format sind meist größer als die anderen Dateien mit unstrukturierten oder "Flatfileformat" gespeichert. Wenn Ihre Anwendung häufig Dateien lädt und speichert, kann die mit compound-Dateien die Dateigröße erhöhen deutlich schneller als Verbunddateien führen. Da Verbunddateien groß werden können, kann die Zugriffszeit für Dateien gespeichert, und Laden von Disketten auch beeinflusst werden resultierende verzögerten Zugriff auf Dateien.

Ein weiteres Problem, das auf die Leistung auswirkt, ist Compound-Dateifragmentierung. Die Größe einer Verbunddatei richtet sich nach den Unterschieden zwischen den vor- und Nachnamen Datenträgersektoren, die von der Datei verwendet. Eine fragmentierte Datei kann viele Bereiche des freien Speicherplatzes enthalten, die enthalten keine Daten werden gezählt, wenn die Größe zu berechnen. Während der Lebensdauer einer Verbunddatei werden diese Bereiche durch das Einfügen oder Löschen von Speicherobjekten erstellt.

##  <a name="_core_using_compound_files_format_for_your_data"></a> Mithilfe von Verbunddateien-Formats für Ihre Daten

Nach dem erfolgreichen Erstellen einer Anwendung, die eine Dokumentklasse abgeleitet wurde `COleDocument`, stellen Sie sicher, dass Ihr Hauptdokument-Konstruktor aufruft `EnableCompoundFile`. Wenn OLE-containeranwendungen mit der Anwendungs-Assistent erstellt wird, wird dieser Aufruf für Sie eingefügt.

In der *OLE-Programmierreferenz*, finden Sie unter [IStream](/windows/desktop/api/objidl/nn-objidl-istream), [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage), und [ILockBytes](/windows/desktop/api/objidl/nn-objidl-ilockbytes).

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)<br/>
[COleStreamFile-Klasse](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument-Klasse](../mfc/reference/coledocument-class.md)
