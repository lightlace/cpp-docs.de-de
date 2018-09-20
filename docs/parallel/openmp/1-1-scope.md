---
title: 1.1 Bereich | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81babf799860030f6d398f64b55ed65039de8649
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393529"
---
# <a name="11-scope"></a>1.1 Bereich

Diese Spezifikation behandelt nur Benutzer-gesteuerte Parallelisierung, bei dem der Benutzer explizit die Aktionen, die durch den Compiler und Laufzeit-System ausgeführt werden, um die Anwendung parallel auszuführen angibt. OpenMP-C- und C++-Implementierungen sind nicht erforderlich, zum Prüfen der Abhängigkeiten, Konflikte, Deadlocks, Racebedingungen oder andere Probleme, die in der falschen programmausführung führen. Der Benutzer ist dafür verantwortlich, sicherzustellen, dass die Anwendung mithilfe der OpenMP-C- und C++-API-Konstrukte ordnungsgemäß ausgeführt wird. Vom Compiler generierter automatische Parallelisierung und Direktiven für den Compiler bei solchen Parallelisierung werden in diesem Dokument nicht behandelt.