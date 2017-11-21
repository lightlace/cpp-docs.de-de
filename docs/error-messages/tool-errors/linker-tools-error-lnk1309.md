---
title: Linkertoolfehler Lnk1309 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1309
dev_langs: C++
helpviewer_keywords: LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: febaeeeabdf045ee7d223b7514d63202ded1e99c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1309"></a>Linkertoolfehler LNK1309
Typ1-Modul gefunden. mit der Option/CLRIMAGETYPE: Typ2 ungültig  
  
 Ein CLR-imagetyps wurde angefordert, mit **/CLRIMAGETYPE** , aber der Linker konnte ein Image dieses Typs erzeugen, da eine oder mehrere Module nicht mit diesem Typ kompatibel sind.  
  
 LNK1309 wird beispielsweise ausgegeben, wenn Sie angeben, **/CLRIMAGETYPE:safe** und übergeben Sie ein Modul mit erstellten **/CLR: pure**.  
  
 Sie sehen auch LNK1309, wenn Sie versuchen, eine teilweise vertrauenswürdige Ptrustu [d] .lib mit reine CLR-Anwendung zu erstellen. Informationen zum Erstellen einer teilweise vertrauenswürdigen Anwendung finden Sie unter [Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit auf der CRT-Bibliothek-DLL](../../dotnet/create-a-partially-trusted-application.md).  
  
 Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [/CLRIMAGETYPE (Angeben der CLR Image-)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).