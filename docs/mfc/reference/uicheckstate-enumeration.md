---
title: UICheckState-Enumeration
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 1411e9b7cb088c063e17cc7c59871e5f0b83ad9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309797"
---
# <a name="uicheckstate-enumeration"></a>UICheckState-Enumeration

Beschreibt den Aktivierungszustand eines Benutzeroberflächenelements für den Befehl.

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

[ICommandUI::Check](icommandui-interface.md#check) verwendet diese Werte, um den Status des eines Benutzeroberflächenelements beschreiben.
Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)
