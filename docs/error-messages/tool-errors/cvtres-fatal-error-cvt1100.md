---
title: 'CVTRES: Schwerwiegender Fehler CVT1100 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CVT1100
dev_langs: C++
helpviewer_keywords: CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba8ea3fdfdea9ca5aa142a1f2a8f15c5d3ac536a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES: Schwerwiegender Fehler CVT1100
doppelte Ressourcen – Typ: Typ, Name: Name, Sprache: Language, Flags: Flags, Größe: Size  
  
 Die angegebene Ressource wurde mehrmals angegeben.  
  
 Sie können diesen Fehler erhalten, wenn der Linker eine Typbibliothek erstellt, und Sie hat keinen [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) und eine Ressource im Projekt bereits 1 verwendet. In diesem Fall geben Sie/TLBID und eine andere Zahl bis 65535.