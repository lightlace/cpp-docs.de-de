---
title: CWinFormsView Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5e82dce1d80ee241c8bffae99457c2e25555818
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121714"
---
# <a name="cwinformsview-class"></a>CWinFormsView-Klasse
Stellt generische Funktionen zum Hosten eines Windows Forms-Steuerelements als MFC-Ansicht bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Erstellt ein `CWinFormsView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsView::](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|name||  
|----------|-|  
|[CWinFormsView::operator Steuerelement ^](#operator_control)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 MFC verwendet die `CWinFormsView` -Klasse zum Hosten von .NET Framework Windows Forms-Steuerelements in MFC-Ansicht. Das Steuerelement ist ein untergeordnetes Element von der Ansicht mit systemeigenen und nimmt den gesamten Clientbereich der MFC-Ansicht. Das Ergebnis ähnelt einer `CFormView` Ansicht, sodass Sie nutzen Windows Forms-Designer und Laufzeit, um umfangreiche formularbasierte Ansichten zu erstellen.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpfen (Projekte, die in der AFXDLL definiert ist).  
  
> [!NOTE]
>  CWinFormsView unterstützt nicht die MFC-Splitterfenster ( [CSplitterWnd Klasse](../../mfc/reference/csplitterwnd-class.md)). Derzeit nur die Windows Forms Splitter-Steuerelement unterstützt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView  
 Erstellt ein `CWinFormsView`-Objekt.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Parameter  
 *pManagedViewType*  
 Ein Zeiger auf den Datentyp des Windows Forms-Benutzersteuerelements.   
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `CUserView` Klasse erbt von `CWinFormsView` und übergibt den Typ des `UserControl1` auf die `CWinFormsView` Konstruktor. `UserControl1` ist ein benutzerspezifisches Steuerelement im ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>  CWinFormsView::  
 Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `System.Windows.Forms.Control` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel zum Verwenden von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>  CWinFormsView::operator Steuerelement ^  
 Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ermöglicht Ihnen das Übergeben einer `CWinFormsView` Ansicht, um Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement des Typs akzeptieren <xref:System.Windows.Forms.Control>.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CWinFormsView::](#getcontrol).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl-Klasse](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)
