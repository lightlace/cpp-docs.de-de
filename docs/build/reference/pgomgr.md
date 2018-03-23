---
title: Pgomgr | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 743665bbe0ee9c3df08d197d203e95d08542f613
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="pgomgr"></a>pgomgr

Die PGD-Datei hinzugefügt Profildaten aus einer oder mehreren PGC-Dateien.

## <a name="syntax"></a>Syntax

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Parameter

*options*<br/>
Die folgenden Optionen können angegeben werden, um **Pgomgr**:

- **/ help** oder **/?** Zeigt die verfügbare **Pgomgr** Optionen.

- **/ clear** bewirkt, dass die PGD-Datei aller Profilinformationen gelöscht werden. Sie können eine PGC nicht angeben Datei wann **/clear** angegeben ist.

- **/ detail** zeigt detaillierte Statistiken, einschließlich Informationen zum Ausführungsfluss Graph Coverage.

- **/ summary** zeigt pro Funktion Statistiken.

- **/ eindeutige** bei Verwendung mit **/summary**, ergänzte Funktionsnamen angezeigt. Die Standardeinstellung, wenn **/ eindeutige** nicht verwendet wird, wird für nicht ergänzten Funktionsnamen angezeigt werden.

- **/ merge**[**: *** n*] bewirkt, dass die Daten in der PGC-Datei oder die Dateien die PGD-Datei hinzugefügt werden. Der optionale Parameter *n*, können Sie angeben, dass die Daten hinzugefügt werden sollen *n* Zeiten. Beispielsweise wäre ein Szenario häufig "Fertig" ändert sechs Mal widerspiegeln, wie oft von Kunden erfolgt, Sie können dafür in einem Testlauf einmal und sechs Mal mit der PGD-Datei hinzugefügt **Pgomgr/Merge: 6**.

*pgcfiles*<br/>
Eine oder mehrere PGC-Dateien, deren Profil für Daten in die PGD-Datei zusammengeführt werden sollen. Sie können eine einzelne PGC-Datei oder mehrere PGC-Dateien angeben. Wenn Sie keine PGC-Dateien angeben **Pgomgr** alle PGC-Dateien, deren Dateinamen identisch mit der PGD-Datei sind, zusammengeführt.

*Pgdfile* die PGD-Datei, in dem Sie Daten aus dem PGC-Datei oder Dateien zusammengeführt werden.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

## <a name="example"></a>Beispiel

Mit diesem Beispielbefehl werden die Datei myapp.pgd von Profildaten gelöscht:

`pgomgr /clear myapp.pgd`

Mit diesem Beispielbefehl hinzugefügt Profildaten in myapp1.pgc die PGD-Datei dreimal:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

In diesem Beispiel werden die Datei myapp.pgd Profildaten aus allen "MyApp" # .pgc-Dateien hinzugefügt.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>Siehe auch

[Profilgesteuerte Optimierungen](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
