---
title: Pgosweep | Microsoft-Dokumentation
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
ms.openlocfilehash: ed12828d9170aac576a97c63b9988bb4b303ef58
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711917"
---
# <a name="pgosweep"></a>pgosweep

Verwendet in der profilgesteuerten Optimierung ein, um alle Profildaten aus einem ausgeführten Programm der PGC-Datei zu schreiben.

## <a name="syntax"></a>Syntax

> **Pgosweep** [*Optionen*] *Image* *Pgcfile*

### <a name="parameters"></a>Parameter

*options*<br/>
(Optional) Die gültigen Werte für *Optionen* sind:

- **/?** oder **/help** zeigt die hilfemeldung an.

- **/ noreset** behält die Anzahl die in die Common Language Runtime-Datenstrukturen.

*Bild*<br/>
Den vollständigen Pfad einer .exe oder .dll-Datei, die mithilfe der [/genprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), oder [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) Option.

*pgcfile*<br/>
Die .pgc-Datei, in dem dieser Befehl die Daten Anzahl schreibt.

## <a name="remarks"></a>Hinweise

Die **Pgosweep** Befehl funktioniert in Programmen, die mithilfe von erstellt wurden die [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) Option oder der veralteten [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) Option. Es ein ausgeführtes Programm unterbricht und schreibt die Profildaten zu einer neuen PGC-Datei. Standardmäßig setzt der Befehl die Anzahl nach jedem Schreibvorgang zurück. Bei Angabe der **/noreset** -Option der Befehl Notieren Sie die Werte, aber nicht in das aktive Programm zurücksetzen. Diese Option erhalten Sie doppelte Daten, wenn Sie die Profildaten später abrufen.

Eine alternative Verwendung für **Pgosweep** besteht darin, Informationen zum Profil nur für den normalen Betrieb der Anwendung abzurufen. Sie können z. B. ausführen **Pgosweep** in Kürze zur Verfügung, nachdem Sie die Anwendung zu starten, und verwerfen die Datei. Dadurch würde Startkosten zugeordnete Profildaten entfernt. Sie können dann ausführen **Pgosweep** vor dem Beenden der Anwendung. Die gesammelten Daten verfügt nun über Profilinformationen nur ab dem Zeitpunkt, dass der Benutzer mit dem Programm interagieren kann.

Wenn Sie eine PGC-Datei benennen (mithilfe der *Pgcfile* Parameter) können Sie das Standardformat, handelt es sich *Appname! n*.pgc. Wenn Sie dieses Format verwenden, sucht der Compiler automatisch diese Daten in die **/LTCG/USERPROFILE angegeben** oder **/LTCG: PGO** Phase. Wenn Sie das Standardformat nicht verwenden, müssen Sie verwenden ["pgomgr"](pgomgr.md) die PGC-Dateien zusammenführen.

> [!NOTE]
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

Informationen zum Erfassen der Profildaten aus innerhalb der ausführbaren Datei, finden Sie unter ["PgoAutoSweep"](pgoautosweep.md).

## <a name="example"></a>Beispiel

In diesem Beispielbefehl **Pgosweep** schreibt die aktuellen Profilinformationen für myapp.exe in MyApp! 1.pgc.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
