---
title: Initialisierungslisten | Microsoft Docs
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
helpviewer_keywords:
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1af020bec295f0f949b7ebb6abe88102f3942b1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initializer-lists"></a>Initialisiererlisten
Initialisierungslisten in Konstruktoren werden jetzt vor dem Konstruktor der Basisklasse aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Visual C++ 2005 wurde der Basisklassenkonstruktor vor der Initialisierungsliste aufgerufen, bevor beim Kompilieren mit Managed Extentions für C++. Jetzt beim Kompilieren mit **"/ CLR"**, die Initialisiererliste zuerst aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)