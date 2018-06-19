---
title: Pgosweep | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ded5b692d7c51e5a46a325a69ad6969083025ff5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378924"
---
# <a name="pgosweep"></a>pgosweep

Bei profilgesteuerter Optimierung verwendet, um alle Profildaten aus ein aktives Programm in die PGC-Datei zu schreiben.

## <a name="syntax"></a>Syntax

> **Pgosweep** [*Optionen*] *Image* *Pgcfile*

### <a name="parameters"></a>Parameter

*Optionen* (optional)<br/>
Die gültigen Werte für *Optionen* sind:

- **/?** oder **/help** zeigt die Hilfe an.

- **/ noreset** behält die Anzahl die in der Common Language Runtime-Datenstrukturen.

*Bild*<br/>
Den vollständigen Pfad einer erstellten .exe oder .dll-Datei der [/genprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), oder [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) Option.

*pgcfile*<br/>
Die PGC-Datei, in dem mit diesem Befehl die Daten Anzahlen ausgeschrieben.

## <a name="remarks"></a>Hinweise

Die **Pgosweep** Befehl funktioniert in Programmen, die mit erstellt wurden die [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) Option oder veralteten [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) Option. Er unterbricht ein aktives Programm, und schreibt die Profildaten zu einer neuen PGC-Datei. Standardmäßig setzt der Befehl Anzahlen nach jedem Schreibvorgang. Bei Angabe der **/noreset** -Option der Befehl Notieren Sie die Werte, aber nicht zurückgesetzt werden sie in der laufenden Anwendung. Diese Option bietet Ihnen doppelte Daten, wenn Sie die Profildaten später abrufen.

Eine alternative Verwendung für **Pgosweep** Profilinformationen nur für die normale Ausführung der Anwendung abrufen. Sie könnten z. B. ausführen **Pgosweep** kurz nach dem Starten der Anwendung und verwerfen die Datei. Dadurch würde Startkosten zugeordnete Profildaten entfernt. Sie können dann ausführen **Pgosweep** vor dem Beenden der Anwendung. Die gesammelten Daten hat jetzt Profilinformationen nur ab dem Zeitpunkt, dass der Benutzer mit dem Programm interagieren kann.

Wenn Sie benennen eine PGC-Datei (mit der *Pgcfile* Parameter) können Sie das Standardformat ist *Appname! n*PGC. Wenn Sie dieses Format verwenden, sucht der Compiler automatisch diese Daten in der **/LTCG/useprofile** oder **/LTCG: PGO** Phase. Wenn Sie das Standardformat nicht verwenden, müssen Sie verwenden [Pgomgr](pgomgr.md) die PGC-Dateien zusammenzuführen.

> [!NOTE]
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

Informationen zum Erfassen der Profildaten aus innerhalb der ausführbaren Datei finden Sie unter [PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Beispiel

In diesem Beispielbefehl **Pgosweep** schreibt die aktuellen Profilinformationen für myapp.exe in MyApp! 1.pgc.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
