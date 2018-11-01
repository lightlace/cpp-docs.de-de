---
title: pgomgr
ms.date: 03/14/2018
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
ms.openlocfilehash: 4e3eb08c88db9d0ed4e47649014a600c3e0ccb78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540503"
---
# <a name="pgomgr"></a>pgomgr

Die .pgd-Datei hinzugefügt Profildaten von einer oder mehreren PGC-Dateien.

## <a name="syntax"></a>Syntax

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parameter

*options*<br/>
Die folgenden Optionen können angegeben werden, um **"pgomgr"**:

- **/ help** oder **/?** Zeigt die verfügbare **"pgomgr"** Optionen.

- **/ clear** bewirkt, dass die PGD-Datei aller Profilinformationen gelöscht werden sollen. Sie nicht angeben, dass eine PGC-Datei beim **/clear** angegeben ist.

- **/ detail** zeigt detaillierte Statistiken, einschließlich eines Diagramms Abdeckungsinformationen.

- **/ summary** zeigt pro Funktion Statistiken.

- **/ unique** bei Verwendung mit **/summary**, ergänzte Funktionsnamen anzeigen. Der Standardwert, wenn **/ eindeutige** nicht verwendet wird, wird für nicht ergänzte Funktionsnamen, die angezeigt werden.

- **/ merge**\[**:**<em>n</em>] führt dazu, dass die Daten in der PGC-Datei oder Dateien, die die PGD-Datei hinzugefügt werden. Der optionale Parameter *n*, können Sie angeben, dass die Daten hinzugefügt werden sollen *n* Zeiten. Z. B. wenn ein Szenario im Allgemeinen fertig sechs Mal ist um widerzuspiegeln, wie oft dies durch den Kunden erfolgt, Sie können sie nur einmal in einem Testlauf und Hinzufügen der PGD-Datei mit sechsmal **"pgomgr" / Merge: 6**.

*pgcfiles*<br/>
Eine oder mehrere PGC-Dateien, deren Profildaten in die PGD-Datei zusammengeführt werden sollen. Sie können eine einzelne PGC-Datei oder mehrere PGC-Dateien angeben. Wenn Sie keine PGC-Dateien, angeben **"pgomgr"** alle PGC-Dateien, deren Dateinamen identisch mit der PGD-Datei sind, zusammengeführt.

*pgdfile*<br/>
Die .pgd-Datei, in der Sie Daten aus der PGC-Datei oder Dateien zusammengeführt werden.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

## <a name="example"></a>Beispiel

Dieser Befehl im Beispiel wird die Datei myapp.pgd von Profildaten gelöscht:

`pgomgr /clear myapp.pgd`

Dieser Beispielbefehl hinzugefügt Profildaten in myapp1.pgc die PGD-Datei drei Mal:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

In diesem Beispiel werden der Datei myapp.pgd Profildaten aus allen Myapp # .pgc-Dateien hinzugefügt.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
