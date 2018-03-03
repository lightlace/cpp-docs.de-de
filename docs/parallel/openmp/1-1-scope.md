---
title: 1.1 Bereich | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07859a95b739cf649ab6516cb2e8b605efe442dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="11-scope"></a>1.1 Bereich
Diese Spezifikation behandelt nur benutzergesteuerten Parallelisierung, bei dem der Benutzer die Aktionen, die durch den Compiler und Laufzeit-System ausgeführt werden, um die Anwendung parallel ausgeführt werden explizit angibt. OpenMP-C- und C++-Implementierungen sind nicht erforderlich, Suchen nach Abhängigkeiten, Konflikte, Deadlocks, Racebedingungen oder andere Probleme, die sich in der falschen programmausführung ergeben. Der Benutzer ist dafür verantwortlich, dass die Anwendung mithilfe der OpenMP-C- und C++-API-Konstrukte ordnungsgemäß ausgeführt wird. Vom Compiler generierte automatische Parallelisierung und Richtlinien für den Compiler solche Parallelisierung zu unterstützen, werden in diesem Dokument nicht behandelt.