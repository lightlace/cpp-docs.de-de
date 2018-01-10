---
title: UICheckState-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afxwinforms/uicheckstate
dev_langs: C++
helpviewer_keywords: uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7feac12853066ad4971d98ce7cf25ec4d8a86fa8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
