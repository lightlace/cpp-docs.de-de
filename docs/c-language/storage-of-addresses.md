---
title: Speicherung von Adressen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd82f6f5046cf910fbc871be37d4af5856796792
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-addresses"></a>Speicherung von Adressen
Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab. Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben. Daher ist **sizeof(char \*)** nicht unbedingt gleich **sizeof(int \*)**.  
  
 **Microsoft-spezifisch**  
  
 Für den Microsoft C-Compiler ist **sizeof(char \*)** gleich **sizeof(int \*)**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Zeigerdeklarationen](../c-language/pointer-declarations.md)