---
title: Projektbuildfehler PRJ0008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7c24634a845423de590228af01cb9f4779e37ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062786"
---
# <a name="project-build-error-prj0008"></a>Projektbuildfehler PRJ0008

Datei 'Datei' konnte nicht gelöscht werden.

**Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**

Während einer Neuerstellung oder Bereinigung, löscht Visual C++ alle bekannten zwischen- und Ausgabedateien Dateien für den Build, sowie alle Dateien, die die Platzhalterspezifikationen in erfüllen die **Erweiterungen bereinigen zu löschende** -Eigenschaft in der [Allgemein Seite für Konfigurationseinstellungen Eigenschaft](../../ide/general-property-page-project.md).

Dieser Fehler wird angezeigt, wenn es sich bei Visual C++ nicht zum Löschen einer Datei kann. Um den Fehler zu beheben, müssen Sie die Datei und das Verzeichnis für den Benutzer, die die Erstellung geschrieben.