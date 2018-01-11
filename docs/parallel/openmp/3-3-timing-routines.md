---
title: 3.3 Routinen zur zeitlichen Steuerung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 21060d64-cbe8-4e38-8718-3a68d6a57be3
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05f9e7c8eedbf1803e1bfbc3c744c5d8b9c9fd99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="33-timing-routines"></a>3.3 Routinen zur zeitlichen Steuerung
Die in diesem Abschnitt beschriebenen Funktionen unterstützen einen portable Realzeit Timer:  
  
-   Die `omp_get_wtime` Funktion gibt die verstrichene wanduhrzeit zurück.  
  
-   Die `omp_get_wtick` Funktion gibt Sekunden zwischen aufeinander folgenden Zeiteinheiten zurück.