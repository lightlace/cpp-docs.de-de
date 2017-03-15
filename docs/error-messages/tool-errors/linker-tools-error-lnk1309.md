---
title: "Linkertoolfehler LNK1309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1309"
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typ1\-Modul gefunden. Ungültig mit Schalter \/CLRIMAGETYPE:Typ2  
  
 Ein CLR\-Bildtyp wurde mit **\/CLRIMAGETYPE** angefordert, der Linker konnte jedoch kein Abbild dieses Typs erstellen, da ein oder mehrere Module nicht mit diesem Typ kompatibel waren.  
  
 LNK1309 wird z. B. ausgegeben, wenn Sie **\/CLRIMAGETYPE:safe** angeben und dann ein Modul übergeben, das mit **\/clr:pure** erstellt wurde.  
  
 Wenn Sie versuchen, unter Verwendung von ptrustu\[d\].lib eine teilweise vertrauenswürdige reine CLR\-Anwendung zu erstellen, wird ebenfalls LNK1309 angezeigt.  Weitere Informationen über das Erstellen einer teilweise vertrauenswürdigen Anwendung finden Sie unter [Gewusst wie: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT\-Bibliotheks\-DLL](../../dotnet/create-a-partially-trusted-application.md).  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) und [\/CLRIMAGETYPE \(Angeben des CLR\-Bildtyps\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).