---
title: CFolderPickerDialog-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 2ca0f618006345d0d36650655a4e62d721b4d4d4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog-Klasse
CFolderPickerDialog-Klasse implementiert CFileDialog im ordnerauswahlmodus.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFolderPickerDialog : public CFileDialog;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Destruktor.|  
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Konstruktor.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
 `CFolderPickerDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cfolderpickerdialog"></a>CFolderPickerDialog::CFolderPickerDialog  
 Konstruktor.  
  
```  
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFolder`  
 Anfängliche Ordner.  
  
 `dwFlags`  
 Eine Kombination von ein oder mehrere Flags, die Sie im Dialogfeld anpassen können.  
  
 `pParentWnd`  
 Ein Zeiger auf die Dialogfeldobjekt über- oder Besitzer Fenster.  
  
 `dwSize`  
 Die Größe des OPENFILENAME-Struktur.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="_dtorcfolderpickerdialog"></a>CFolderPickerDialog:: ~ CFolderPickerDialog  
 Destruktor.  
  
```  
virtual ~CFolderPickerDialog();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

