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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8a9a2b431a6f064d4593a547092a7e6dcf60dadd
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-addresses"></a>Speicherung von Adressen
Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab. Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben. Daher ist **sizeof(char \*)** nicht unbedingt gleich **sizeof(int \*)**.  
  
 **Microsoft-spezifisch**  
  
 Für den Microsoft C-Compiler ist **sizeof(char \*)** gleich **sizeof(int \*)**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Zeigerdeklarationen](../c-language/pointer-declarations.md)
