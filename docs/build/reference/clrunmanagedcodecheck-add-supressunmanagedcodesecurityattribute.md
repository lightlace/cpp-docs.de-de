---
title: "-CLRUNMANAGEDCODECHECK (Hinzufügen von SuppressUnmanagedCodeSecurity-Attribut) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f32ae791ebb09d3d2cfced48c42f982580e69b63
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (Hinzufügen von SuppressUnmanagedCodeSecurity-Attribut)
**/ CLRUNMANAGEDCODECHECK** gibt an, ob der Linker anwendet <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> auf vom Linker generierte `PInvoke` Aufrufe von verwaltetem Code aus systemeigene DLLs.  
  
## <a name="syntax"></a>Syntax  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig übernimmt der Linker den SuppressUnmanagedCodeSecurityAttribute auf vom Linker generierte `PInvoke` aufrufen. Wenn **/CLRUNMANAGEDCODECHECK** ist faktisch SuppressUnmanagedCodeSecurityAttribute nicht übernommen.  
  
 Der Linker fügt das Attribut nur auf Objekte, die mit kompiliert werden, **"/ CLR"** oder **/CLR: pure**. Allerdings die **/CLR: pure** und **/CLR: safe** Compileroptionen sind in Visual Studio 2015 als veraltet markiert und wird in einer zukünftigen Version des Compilers entfernt.  
  
 Ein `PInvoke` Aufruf wird vom Linker generiert, wenn der Linker kann kein verwaltetes Symbol, um einen Verweis von einem verwalteten Aufrufer zu erfüllen, jedoch ein systemeigenes Symbol erfüllen diesen Verweis gefunden. Weitere Informationen zu `PInvoke`, finden Sie unter [Aufrufen systemeigener Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Beachten Sie, dass bei Verwendung von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in Ihrem Code sollten Sie explizit festlegen **/CLRUNMANAGEDCODECHECK**. Es ist Sicherheitsrisiko, wenn ein Bild sowohl die AllowPartiallyTrustedCallers das SuppressUnmanagedCodeSecurity-Attribute enthält.  
  
 Finden Sie unter [Codierungsrichtlinien für nicht verwalteten Code Secure](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) für Weitere Informationen zu den Auswirkungen der Verwendung von SuppressUnmanagedCodeSecurityAttribute.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
5.  Ändern der **nicht verwalteten CLR-Code überprüfen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)