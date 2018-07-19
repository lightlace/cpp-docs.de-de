---
title: Externe Verknüpfung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43301686d5bdb964cf08e8123ff4c55475228567
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383201"
---
# <a name="external-linkage"></a>Externe Verknüpfung
Wenn die erste Deklaration auf Dateigültigkeitsebene für einen Bezeichner nicht den **static**-Speicherklassenspezifizierer verwendet, verfügt das Objekt über eine externe Bindung.  
  
 Wenn die Deklaration eines Bezeichners für eine Funktion über keinen *storage-class-specifier* verfügt, wird seine Bindung genauso bestimmt, als ob sie mit dem *storage-class-specifier* `extern` deklariert worden wäre. Wenn die Deklaration eines Bezeichners für ein Objekt dateiweit gilt und keinen *storage-class-specifier* enthält, ist die Bindung extern.  
  
 Der Name eines Bezeichners mit externer Bindung legt dieselbe Funktion oder dasselbe Datenobjekt fest wie jede andere Deklaration für denselben Namen mit externer Bindung. Die beiden Deklarationen können sich in derselben Übersetzungseinheit oder in verschiedenen Übersetzungseinheiten befinden. Wenn das Objekt oder die Funktion auch eine globale Lebensdauer besitzt, ist das Objekt oder die Funktion im gesamten Programm verfügbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)