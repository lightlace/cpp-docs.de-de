---
title: 1.1 Bereich | Microsoft Docs
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
ms.openlocfilehash: 48d14ec722299a9ff72ad5bab0a68cde5e00d6ad
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="11-scope"></a>1.1 Bereich
Diese Spezifikation behandelt nur benutzergesteuerten Parallelisierung, bei dem der Benutzer die Aktionen, die durch den Compiler und Laufzeit-System ausgeführt werden, um die Anwendung parallel ausgeführt werden explizit angibt. OpenMP-C- und C++-Implementierungen sind nicht erforderlich, Suchen nach Abhängigkeiten, Konflikte, Deadlocks, Racebedingungen oder andere Probleme, die sich in der falschen programmausführung ergeben. Der Benutzer ist dafür verantwortlich, dass die Anwendung mithilfe der OpenMP-C- und C++-API-Konstrukte ordnungsgemäß ausgeführt wird. Vom Compiler generierte automatische Parallelisierung und Richtlinien für den Compiler solche Parallelisierung zu unterstützen, werden in diesem Dokument nicht behandelt.