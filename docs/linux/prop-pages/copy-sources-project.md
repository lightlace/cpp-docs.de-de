---
title: Kopieren von Quellprojekteigenschaften (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: d13bc7c129696e2b7251ccb23b68338956864321
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325590"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kopieren von Quellprojekteigenschaften (Linux C++)

Die auf dieser Eigenschaftenseite festgelegten Eigenschaften gelten für alle Dateien im Projekt, mit Ausnahme derjenigen, deren Eigenschaften auf Dateiebene festgelegt sind.

Eigenschaft | description
--- | ---
Zu kopierende Quellen | Gibt die Quellen an, die auf das Remotesystem kopiert werden sollen. Das Ändern dieser Liste kann die Verzeichnisstruktur, in die Dateien auf dem Remotesystem kopiert werden, verschieben oder anderweitig beeinflussen.
Kopieren der Quellen | Gibt an, ob die Quellen auf das Remotesystem kopiert werden sollen.
Zusätzliche zu kopierende Quellen | Gibt zusätzliche Quellen an, die auf das Remotesystem kopiert werden sollen. Optional kann die Liste als Zuordnungspaare zwischen lokal und remote mit der folgenden Syntax bereitgestellt werden: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2. Dabei kann eine lokale Datei an den angegebenen Remotespeicherort auf dem Remotesystem kopiert werden.
