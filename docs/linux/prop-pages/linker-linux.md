---
title: Linkereigenschaften (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 9187222d2ced21ece2f183655591c483abc8d500
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-properties-linux-c"></a>Linkereigenschaften (Linux C++)

## <a name="general"></a>Allgemein

Eigenschaft | description | Auswahlmöglichkeiten
--- | ---| ---
Ausgabedatei | Die Option überschreibt den Standardnamen und den Speicherort des Programms, das der Linker erstellt. (-o)
Status anzeigen | Gibt Linkerstatusmeldungen aus.
Version | Die Option -version weist den Linker an, eine Versionsnummer in den Header der ausführbaren Datei einzufügen.
Ausführliche Ausgabe aktivieren | Die Option -verbose weist den Linker an, ausführliche Meldungen zum Debuggen auszugeben.
Ablaufverfolgung | Die Option --trace weist den Linker an, die Eingabedateien so auszugeben, wie sie verarbeitet werden.
Ablaufverfolgungssymbole | Gibt die Liste der Dateien aus, in denen ein Symbol vorkommt. (--trace-symbol=symbol)
Zuordnung ausgeben | Die Option --print-map weist den Linker an, eine Linkzuordnung auszugeben.
Nicht aufgelöste Symbolverweise melden | Wenn diese Option aktiviert ist, werden ungelöste Symbolverweise gemeldet.
Für Speicherverbrauch optimieren | Optimiert den Speicherverbrauch, indem die Symboltabellen bei Bedarf erneut gelesen werden.
Suchpfad freigegebene Bibliothek | Ermöglicht dem Benutzer, den Suchpfad für die freigegebene Bibliothek mit Daten aufzufüllen. (-rpath-link=path)
Zusätzliche Bibliotheksverzeichnisse | Ermöglicht dem Benutzer das Überschreiben des umgebungsbedingten Bibliothekspfads. (-L Ordner).
Linker | Gibt das Programm an, das beim Linken aufgerufen werden soll, oder den Pfad zum Linker auf dem Remotesystem.
Linktimeout | Timeout für Remotelinking in Millisekunden.
Ausgabe kopieren | Gibt an, ob die Buildausgabedatei vom Remotesystem auf den lokalen Computer kopiert werden soll.

## <a name="input"></a>Eingabe

Eigenschaft | description | Auswahlmöglichkeiten
--- | ---| ---
Bestimmte Standardbibliotheken ignorieren | Gibt einen oder mehrere Namen der zu ignorierenden Standardbibliotheken an. (--exclude-libs lib,lib)
Standardbibliotheken ignorieren | Ignoriert Standardbibliotheken und sucht nur nach explizit angegebenen Bibliotheken.
Nicht definierte Symbolverweise erzwingen | Erzwingt, dass das Symbol als undefiniertes Symbol in die Ausgabedatei eingegeben wird. (-u symbol --undefined=symbol)
Bibliothekabhängigkeiten | Mit dieser Option können zusätzliche Bibliotheken angegeben werden, die der Linkerbefehlszeile hinzugefügt werden sollen. Die zusätzliche Bibliothek wird am Ende der Linkerbefehlszeile mit dem Präfix „lib“ hinzugefügt und endet auf die Erweiterung „.a“.  (-lFILE)
Zusätzliche Abhängigkeiten | Gibt zusätzliche Elemente an, die der Linkerbefehlszeile hinzugefügt werden sollen.

## <a name="debugging"></a>Debuggen

Eigenschaft | description | Auswahlmöglichkeiten
--- | ---| ---
Debuggersymbolinformationen | Debuggersymbolinformationen aus der Ausgabedatei. | **Alle einschließen**<br>**Nur Debuggersymbolinformationen auslassen**<br>**Alle Symbolinformationen auslassen**<br>
Name der Zuordnungsdatei | Die Option Map weist den Linker an, eine Zuordnungsdatei mit dem vom Benutzer angegebenen Namen zu erstellen. (-Map=)

## <a name="advanced"></a>Erweitert

Eigenschaft | description | Auswahlmöglichkeiten
--- | ---| ---
Variablen nach dem Umsetzen als ReadOnly kennzeichnen | Diese Option kennzeichnet Variablen nach dem Umsetzen als schreibgeschützt.
Sofortige Funktionsbindung aktivieren | Diese Option kennzeichnet das Objekt für sofortige Funktionsbindung.
Keinen ausführbaren Stapel erfordern | Diese Option gibt an, dass die Ausgabe keinen ausführbaren Stapel erfordert.
Gesamtes Archiv | Diese Option verwendet den gesamten Code aus den Quellen und zusätzlichen Abhängigkeiten.
