---
title: IDL-Attribute, Assistent zum Hinzufügen von Methoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea2f0cd3ae445c4804738567b5bd9265363995e3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705157"
---
# <a name="idl-attributes-add-method-wizard"></a>IDL-Attribute, Assistent zum Hinzufügen von Methoden
Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Methoden, um IDL-Einstellungen (Interface Definiton Language) für die Methode anzugeben.  
  
- **ID**

   Legt die numerische ID fest, die die Methode identifiziert. Informationen finden Sie in der *MIDL-Referenz* unter [id](/windows/desktop/Midl/id).  
  
   Dieses Feld ist für benutzerdefinierte Schnittstellen und MFC-Disp-Schnittstellen nicht verfügbar.  
  
- **call_as**

   Gibt den Namen einer Remotemethode an, der die lokale Methode zugeordnet werden kann. Informationen finden Sie in der *MIDL-Referenz* unter [call_as](/windows/desktop/Midl/call-as).  
  
   Nicht für MFC-Disp-Schnittstellen verfügbar.  
  
- **helpcontext**

   Gibt eine Kontext-ID an, die das Anzeigen von Informationen über diese Methode in der Hilfedatei ermöglicht. Informationen finden Sie in der *MIDL-Referenz* unter [helpcontext](/windows/desktop/Midl/helpcontext).  
  
   Nicht für MFC-Disp-Schnittstellen verfügbar.  
  
- **helpstring**

   Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird. Sie ist standardmäßig auf „method *Methodenname*“ festgelegt. Informationen finden Sie in der *MIDL-Referenz* unter [helpstring](/windows/desktop/Midl/helpstring).  
  
   Nicht für MFC-Disp-Schnittstellen verfügbar.  
  
- **Zusätzliche Attribute**

   Nicht für MFC-Disp-Schnittstellen verfügbar.  
  
   |Attribut|Beschreibung |  
   |---------------|-----------------|  
   |**hidden**|Gibt an, dass die Methode vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden sollte. Informationen finden Sie in der *MIDL-Referenz* unter [hidden](/windows/desktop/Midl/hidden).|  
   |**source**|Gibt an, dass ein Member dieser Methode eine Ereignisquelle ist. Informationen finden Sie in der *MIDL-Referenz* unter [source](/windows/desktop/Midl/source).|  
   |`local`|Gibt für den MIDL-Compiler an, dass die Methode lokal ist. Informationen finden Sie in der *MIDL-Referenz* unter [local](/windows/desktop/Midl/local).|  
   |**restricted**|Gibt an, dass die Methode nicht beliebig aufgerufen werden kann. Informationen finden Sie in der *MIDL-Referenz* unter [restricted](/windows/desktop/Midl/restricted).|  
   |**vararg**|Gibt an, dass die Methode eine variable Anzahl von Argumenten akzeptiert. Das letzte Argument muss ein sicheres Array des Typs **VARIANT** sein, das alle übrigen Argumente enthält. Informationen finden Sie in der *MIDL-Referenz* unter [vararg](/windows/desktop/Midl/vararg).|  
  
## <a name="see-also"></a>Siehe auch  
 [Adding a Method (Hinzufügen einer Methode)](../ide/adding-a-method-visual-cpp.md)   
 [Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md)