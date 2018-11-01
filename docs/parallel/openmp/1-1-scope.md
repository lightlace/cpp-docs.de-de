---
title: 1.1 Bereich
ms.date: 11/04/2016
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
ms.openlocfilehash: f87f631ae2d36662daa2ece4790170c00c5cbeb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449204"
---
# <a name="11-scope"></a>1.1 Bereich

Diese Spezifikation behandelt nur Benutzer-gesteuerte Parallelisierung, bei dem der Benutzer explizit die Aktionen, die durch den Compiler und Laufzeit-System ausgeführt werden, um die Anwendung parallel auszuführen angibt. OpenMP-C- und C++-Implementierungen sind nicht erforderlich, zum Prüfen der Abhängigkeiten, Konflikte, Deadlocks, Racebedingungen oder andere Probleme, die in der falschen programmausführung führen. Der Benutzer ist dafür verantwortlich, sicherzustellen, dass die Anwendung mithilfe der OpenMP-C- und C++-API-Konstrukte ordnungsgemäß ausgeführt wird. Vom Compiler generierter automatische Parallelisierung und Direktiven für den Compiler bei solchen Parallelisierung werden in diesem Dokument nicht behandelt.