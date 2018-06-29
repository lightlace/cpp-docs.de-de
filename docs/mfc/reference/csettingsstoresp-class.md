---
title: CSettingsStoreSP Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9b7cdc0d75ec207e3bd8141ac3a0f9c5ce1d3eb
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078698"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP-Klasse
Die `CSettingsStoreSP` Klasse ist eine Hilfsklasse, die Sie, zum Erstellen von Instanzen verwenden können der [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Erstellt ein `CSettingsStoreSP`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Erstellt eine Instanz einer Klasse, die abgeleitet ist `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Legt die Common Language Runtime-Klasse. Die `Create` Methode verwendet die Common Language Runtime-Klasse, um zu bestimmen, welche Klasse von Objekten zu erstellen.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_dwUserData`|Benutzerdefinierte Daten, die in gespeichert ist die `CSettingsStoreSP` Objekt. Geben Sie diese Daten im Konstruktor der der `CSettingsStoreSP` Objekt.|  
|`m_pRegistry`|Die `CSettingsStore`-abgeleitete Objekt, mit der `Create` Methode erstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `CSettingsStoreSP` Klasse, um alle MFC-Registrierungsvorgänge an anderen Speicherorten, z. B. eine XML-Datei oder einer Datenbank umleiten. Führen Sie dazu folgende Schritte aus:  
  
1.  Erstellen Sie eine Klasse (z. B. `CMyStore`) und leiten sie von `CSettingsStore`.  
  
2.  Verwendung [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) und [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) Makros mit Ihrer benutzerdefinierten `CSettingsStore` Klasse, um die dynamische Erstellung zu ermöglichen.  
  
3.  Virtuellen Funktionen überschreiben und Implementieren der `Read` und `Write` Funktionen in Ihre benutzerdefinierte Klasse. Implementieren Sie eine beliebige andere Funktionen zum Lesen und Schreiben von Daten an die gewünschte Position.  
  
4.  Rufen Sie in der Anwendung `CSettingsStoreSP::SetRuntimeClass` und übergeben Sie einen Zeiger auf die [CRuntimeClass Struktur](../../mfc/reference/cruntimeclass-structure.md) von Ihrer Klasse abgerufen.  
  
 Wenn das Framework in der Regel auf die Registrierung zugreifen würden, werden jetzt dynamisch Ihre benutzerdefinierte Klasse zu instanziieren und verwenden, um die Daten lesen oder schreiben.  
  
 `CSettingsStoreSP::SetRuntimeClass` verwendet eine globale statische Variable. Deshalb steht nur einen benutzerdefinierten Speicher zu einem Zeitpunkt zur Verfügung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsettingsstore.h  
  
##  <a name="create"></a>  CSettingsStoreSP::Create  
 Erstellt eine neue Instanz eines Objekts, das von abgeleitet ist die [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAdminpfad*  
 Ein boolescher Parameter, der bestimmt, ob ein `CSettingsStore` Objekt wird erstellt, im Administratormodus.  
  
 [in] *bReadOnly*  
 Ein boolescher Parameter, der bestimmt, ob eine `CSettingsStore` Objekt wird für nur-Lese-Zugriff erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das neu erstellte `CSettingsStore` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können mithilfe der Methode [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) um zu bestimmen, welche Art von Objekt `CSettingsStoreSP::Create` wird erstellt. Diese Methode erstellt standardmäßig eine `CSettingsStore` Objekt.  
  
 Wenn Sie erstellen ein `CSettingsStore` -Objekt im Administratormodus, der Standardspeicherort für alle Registrierungszugriff HKEY_LOCAL_MACHINE. Andernfalls ist der Standardspeicherort für alle Registrierungszugriff HKEY_CURRENT_USER.  
  
 Wenn *bAdminpfad* ist `TRUE`, die Anwendung muss über Administratorrechte verfügen. Andernfalls schlägt er fehl, wenn er versucht, auf die Registrierung zugreifen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CSettingsStoreSP` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP  
 Erstellt eine [CSettingsStoreSP Klasse](../../mfc/reference/csettingsstoresp-class.md) Objekt.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwUserData*  
 Benutzerdefinierte Daten, die die `CSettingsStoreSP` -Objekt speichert.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSettingsStoreSP` Objekt speichert die Daten aus *DwUserData* in der geschützten Membervariablen `m_dwUserData`.  
  
##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass  
 Legt die Common Language Runtime-Klasse. Die Methode [CSettingsStoreSP::Create](#create) verwendet die Common Language Runtime-Klasse, um zu bestimmen, welche Art des zu erstellenden Objekts.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pRTI*  
 Ein Zeiger auf die laufzeitklasseninformationen für eine Klasse abgeleitet wurde. die [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Bei Erfolg; `FALSE` Wenn von die Klasse identifiziert *pRTI* stammt nicht aus `CSettingsStore`.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie die [CSettingsStoreSP Klasse](../../mfc/reference/csettingsstoresp-class.md) zum Ableiten von Klassen `CSettingsStore`. Verwenden Sie die Methode `SetRuntimeClass` Wunsch Objekte einer benutzerdefinierten Klasse erstellen, die abgeleitet ist `CSettingsStore`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md)
