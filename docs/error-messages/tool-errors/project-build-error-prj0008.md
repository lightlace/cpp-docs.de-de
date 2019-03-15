---
title: Projektbuildfehler PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 5741b7ef8cb9a7ae53d64874d3531e9271c09e0f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815995"
---
# <a name="project-build-error-prj0008"></a>Projektbuildfehler PRJ0008

Datei 'Datei' konnte nicht gelöscht werden.

**Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**

Während einer Neuerstellung oder Bereinigung, löscht Visual C++ alle bekannten zwischen- und Ausgabedateien Dateien für den Build, sowie alle Dateien, die die Platzhalterspezifikationen in erfüllen die **Erweiterungen bereinigen zu löschende** -Eigenschaft in der [Allgemein Seite für Konfigurationseinstellungen Eigenschaft](../../build/reference/general-property-page-project.md).

Dieser Fehler wird angezeigt, wenn es sich bei Visual C++ nicht zum Löschen einer Datei kann. Um den Fehler zu beheben, müssen Sie die Datei und das Verzeichnis für den Benutzer, die die Erstellung geschrieben.