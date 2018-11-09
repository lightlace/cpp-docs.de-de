---
title: Kopieren von Quellprojekteigenschaften (Linux C++)
ms.date: 9/26/2017
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: dd0a26db58265724f0a0e46c31365c97c00ff568
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477245"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kopieren von Quellprojekteigenschaften (Linux C++)

Die auf dieser Eigenschaftenseite festgelegten Eigenschaften gelten für alle Dateien im Projekt, mit Ausnahme derjenigen, deren Eigenschaften auf Dateiebene festgelegt sind.

Eigenschaft | Beschreibung 
--- | ---
Zu kopierende Quellen | Gibt die Quellen an, die auf das Remotesystem kopiert werden sollen. Das Ändern dieser Liste kann die Verzeichnisstruktur, in die Dateien auf dem Remotesystem kopiert werden, verschieben oder anderweitig beeinflussen.
Kopieren der Quellen | Gibt an, ob die Quellen auf das Remotesystem kopiert werden sollen.
Zusätzliche zu kopierende Quellen | Gibt zusätzliche Quellen an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.
