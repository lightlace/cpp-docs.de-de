---
title: Kopieren von Quellprojekteigenschaften (Linux C++) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 586244da6cc8c0a682146caf3ea75bdf72b5824e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="copy-sources-project-properties-linux-c"></a>Kopieren von Quellprojekteigenschaften (Linux C++)

Die auf dieser Eigenschaftenseite festgelegten Eigenschaften gelten für alle Dateien im Projekt, mit Ausnahme derjenigen, deren Eigenschaften auf Dateiebene festgelegt sind.

Eigenschaft | description
--- | ---
Zu kopierende Quellen | Gibt die Quellen an, die auf das Remotesystem kopiert werden sollen. Das Ändern dieser Liste kann die Verzeichnisstruktur, in die Dateien auf dem Remotesystem kopiert werden, verschieben oder anderweitig beeinflussen.
Kopieren der Quellen | Gibt an, ob die Quellen auf das Remotesystem kopiert werden sollen.
Zusätzliche zu kopierende Quellen | Gibt zusätzliche Quellen an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.
