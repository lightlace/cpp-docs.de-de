---
title: -DEBUGTYPE (Debuginformationsoptionen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /debugtype
dev_langs: C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7532f0ceb39db4ff2ff44a6cca9076034ece3114
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="debugtype-debug-info-options"></a>/ DEBUGTYPE (Debuginformationsoptionen)
Die Option „/DEBUGTYPE“ gibt die Typen der durch die Option „/DEBUG“ generierten Debuginformationen an.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>Argumente  
 CV  
 Weist den Linker an, Debuginformationen für Symbole, Zeilennummern und andere Objektkompilierungsinformationen in der PDB-Datei auszugeben. Diese Option ist standardmäßig aktiviert beim **/DEBUG** angegeben ist und **DEBUGTYPE** nicht angegeben wird.  
  
 PDATA  
 Weist den Linker an, den Debugstreaminformationen in der PDB-Datei PDATA- und XDATA-Einträge hinzuzufügen. Diese Option ist standardmäßig aktiviert Wenn sowohl die **/DEBUG** und **/Driver** Optionen angegeben werden. Wenn **/DEBUGTYPE:PDATA** angegeben wird, der Linker Debugsymbole automatisch in der PDB-Datei. Wenn **/DEBUGTYPE:PDATA FIXUP** angegeben ist, wird der Linker enthält keine Debugsymbole in die PDB-Datei.  
  
 FIXUP  
 Weist den Linker an, den Debugstreaminformationen in der PDB-Datei Umsetzungstabelleneinträge hinzuzufügen. Diese Option ist standardmäßig aktiviert Wenn sowohl die **/DEBUG** und **/PROFILE** Optionen angegeben werden. Wenn **/DEBUGTYPE:FIXUP** oder **/DEBUGTYPE:FIXUP PDATA** angegeben ist, wird der Linker enthält keine Debugsymbole in die PDB-Datei.  
  
 Argumente für **DEBUGTYPE** können in beliebiger Reihenfolge kombiniert werden, indem Sie sie durch ein Komma. Die **DEBUGTYPE** Option und ihrer Argumente wird keine Groß-/Kleinschreibung beachtet.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der **DEBUGTYPE** Option aus, um die Einbindung der Verschiebung-Tabelle- oder der pdata- und XData-Headerinformationen im Debugstream anzugeben. Dadurch schließt der Linker Informationen über Benutzermoduscode mit ein, der in einem Kerneldebugger sichtbar ist, wenn die Aufschlüsselung in einen Kernelmoduscode erfolgt. Um Debugsymbole zur Verfügung stellen, wenn **FIXUP** wird angegeben, umfassen die **CV** Argument.  
  
 So debuggen Sie Code im Benutzermodus, der für Anwendungen typisch ist, die **DEBUGTYPE** Option ist nicht erforderlich. Wird standardmäßig der Compilerschalter, die angeben, Debuggen von Ausgabe (["/ Z7", / Zi, / Zi](../../build/reference/z7-zi-zi-debug-information-format.md)) alle Informationen benötigt durch den Visual Studio debugger ausgeben. Verwendung **/DEBUGTYPE:PDATA** oder **/DEBUGTYPE:CV, PDATA FIXUP** , Code zu debuggen, die im Benutzermodus und im Kernelmodus-Komponenten, z. B. eine Konfigurations-app für einen Gerätetreiber kombiniert. Weitere Informationen über kernelmodusdebugger finden Sie unter [Debugtools für Windows (WinDbg, KD, CDB, NTSD)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## <a name="see-also"></a>Siehe auch  
 [/ DEBUG (Debuginfo generieren)](../../build/reference/debug-generate-debug-info.md)   
 [/ DRIVER (Treiber für Windows NT-Kernel-Modus)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/ PROFILE (Leistungstools-Profiler)](../../build/reference/profile-performance-tools-profiler.md)   
 [Debugtools für Windows (WinDbg, KD, CDB, NTSD)](http://go.microsoft.com/fwlink/p?LinkID=285651)