---
title: CMFCImageEditorDialog-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 795e5548e93323af389c3faeaefa7dda0bf7d80c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog-Klasse
Die `CMFCImageEditorDialog` Klasse unterstützt ein bildbearbeitungs-Dialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Erstellt ein `CMFCImageEditorDialog`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCImageEditorDialog` -Klasse stellt ein Dialogfeld umfasst:  
  
-   Ein Bildbereich, mit denen Sie einzelne Pixel in einem Bild zu ändern.  
  
-   Zeichnen die Tools, um die Pixel im Bereich "Bild" zu ändern.  
  
-   Eine Farbpalette an die Farbe, die von den Zeichentools verwendet wird.  
  
-   Eine Preview-Bereich, in dem die Auswirkungen der Bearbeitung angezeigt.  
  
 Die folgende Abbildung zeigt eine Grafik-Editor (Dialogfeld).  
  
 ![CMFCImageEditorDialog-Dialogfeld](../../mfc/reference/media/imageedit.png "Imageedit")  
  
 Eine Möglichkeit zum Verwenden einer `CMFCImageEditorDialog` Objekt ist das Übergeben einer `CBitmap` Bild, das bearbeitet werden. Ein großes Bild kann nicht erstellt werden, da das Bild, das Bearbeiten von Bereich einen begrenzten Größe und die logischen Pixelgröße angepasst wird, um den Bereich passt. Rufen Sie die `DoModal` Methode, um ein modales Dialogfeld starten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximageeditordialog.h  
  
##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog  
 Erstellt ein `CMFCImageEditorDialog`-Objekt.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Ein Zeiger auf ein Bild.  
  
 `pParent`  
 Ein Zeiger auf das übergeordnete Fenster für das aktuelle Bild-Editor (Dialogfeld).  
  
 `nBitsPixel`  
 Die Anzahl der Bits verwendet, um die Farbe eines einzelnen Pixels darzustellen, die auch als Farbtiefe bezeichnet wird.  Wenn die `nBitsPixel` Parameter ist-1, die Farbtiefe stammt aus dem Image gemäß der `pBitmap` Parameter. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Um ein Bild zu ändern, übergeben Sie einen Image-Zeiger auf die `CMFCImageEditorDialog` Konstruktor. Rufen Sie anschließend die `DoModal` Methode, um ein modales Dialogfeld zu öffnen. Wenn die `DoModal` Methode zurückgegeben wird, enthält das Bitmuster das neue Image.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCImageEditorDialog` Klasse. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)
