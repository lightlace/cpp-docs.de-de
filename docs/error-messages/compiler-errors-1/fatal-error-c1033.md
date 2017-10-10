---
title: Schwerwiegender Fehler C1033 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1033
dev_langs:
- C++
helpviewer_keywords:
- C1033
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a0c9c67d23f2d0b957fb3e43844245029efedc64
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1033"></a>Schwerwiegender Fehler C1033
Programmdatenbank Pdb kann nicht geöffnet werden.  
  
 Dieser Fehler kann durch Datenträgerfehler verursacht werden.  
  
 In Visual C++ .NET 2002 muss das Benutzergebietsschema richtig festgelegt werden, wenn der Dateiname (oder der Verzeichnispfad zum Dateinamen) MBCS-Zeichen enthält. Das Festlegen des Systemgebietsschemas ist nicht ausreichend; das Benutzergebietsschema muss festgelegt werden, damit MBCS-Zeichen verarbeitet werden.  
  
 Weitere Informationen finden Sie unter [http://support.microsoft.com/default.aspx?scid=kb;en-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).
