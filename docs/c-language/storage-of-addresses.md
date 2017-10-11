---
title: Speicherung von Adressen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 3d0e996ac191ba3091925a85937e7636a2425215
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="storage-of-addresses"></a>Speicherung von Adressen
Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab. Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben. Daher ist **sizeof(char \*)** nicht unbedingt gleich **sizeof(int \*)**.  
  
 **Microsoft-spezifisch**  
  
 Für den Microsoft C-Compiler ist **sizeof(char \*)** gleich **sizeof(int \*)**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Zeigerdeklarationen](../c-language/pointer-declarations.md)
