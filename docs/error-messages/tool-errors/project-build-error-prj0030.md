---
title: Projektbuildfehler prj0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf1c9137f8c4ed0d80955eef38b07ea86204a5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317657"
---
# <a name="project-build-error-prj0030"></a>Projektbuildfehler PRJ0030
Fehler beim Makro-Erweiterung. Werten Sie Rekursion überschritten 32 Ebenen für $(Makro).  
  
 Dieser Fehler wird durch Rekursion in den Makros verursacht. Wenn Sie festlegen, z. B. die **Zwischenverzeichnis** Eigenschaft (finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md)) auf $(intdir), werden Sie Rekursion haben.  
  
 Um diesen Fehler zu beheben, legen Sie keine Makros oder Eigenschaften in Bezug auf die Makros, die sie verwendet werden, um zu definieren.