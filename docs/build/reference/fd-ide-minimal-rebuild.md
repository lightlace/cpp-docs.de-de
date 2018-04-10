---
title: -FD (minimale Neuerstellung in der IDE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /FD
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0dfcf34be03204b920e5a4459c6a2d7ea6c506d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimale Neuerstellung in der IDE)
**/ Fd** ist nicht verfügbar gemacht, für Benutzer mit Ausnahme der [Befehlszeile](../../ide/command-line-property-pages.md) Eigenschaftenseite eines C++-Projekts **Eigenschaftenseiten** Dialogfeld, wenn und nur wenn  [ /GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) nicht ebenfalls ausgewählt. **/ Fd** wirkt sich nicht nur in der Entwicklungsumgebung. **/ Fd** ist nicht verfügbar gemacht, in der Ausgabe von **cl /?**.  
  
 Wenn Sie nicht aktivieren **/GM** in der Entwicklungsumgebung **/FD** verwendet werden. **/ Fd** wird sichergestellt, dass die IDB-Datei über ausreichende Abhängigkeitsinformationen verfügt. **/ Fd** wird nur von der Entwicklungsumgebung verwendet und sollte nicht über die Befehlszeile oder ein Buildskript verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)