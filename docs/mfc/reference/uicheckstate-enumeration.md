---
title: UICheckState-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxwinforms/uicheckstate
dev_langs:
- C++
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 21b23efdbad9f2b867b104d0a0d9d0bbb4338e5a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---

# <a name="uicheckstate-enumeration"></a>UICheckState-Enumeration
Beschreibt den Aktivierungszustand des Elements eine Benutzer-Schnittstelle für den Befehl.  
   
### <a name="syntax"></a>Syntax   
```  
public enum class 
{  
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]  
   Unchecked,   
   Checked,   
   Indeterminate 
};  
```  
   
### <a name="remarks"></a>Hinweise  
 [ICommandUI::Check](icommandui-interface.md#check) verwendet diese Werte, um den Status eines Elements Schnittstelle Benutzer beschreiben.    
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  

