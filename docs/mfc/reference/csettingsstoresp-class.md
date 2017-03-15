---
title: Klasse CSettingsStoreSP | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP class
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 00131a3c03fdb2c1c1de247a8e1bdcfd9beaf852
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP-Klasse
Die `CSettingsStoreSP` Klasse ist eine Hilfsklasse, die Sie, zum Erstellen von Instanzen von verwenden können der [CSettingsStore Klasse](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Erstellt ein `CSettingsStoreSP`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Erstellt eine Instanz einer Klasse, die von abgeleitet ist `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Festlegen der Common Language Runtime-Klasse. Die `Create` -Methode bestimmt die Common Language Runtime-Klasse, welche Klasse von Objekten zu erstellen.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`m_dwUserData`|Benutzerdefinierte Daten, die in gespeichert ist die `CSettingsStoreSP` Objekt. Geben Sie diese Daten in den Konstruktor von den `CSettingsStoreSP` Objekt.|  
|`m_pRegistry`|Die `CSettingsStore`-abgeleitete Objekt, das `Create` -Methode erstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `CSettingsStoreSP` Klasse alle MFC-Registrierungsvorgänge an anderen Orten, z. B. eine XML-Datei oder einer Datenbank umleiten. Führen Sie dazu folgende Schritte aus:  
  
1.  Erstellen Sie eine Klasse (z. B. `CMyStore`) und leiten sie von `CSettingsStore`.  
  
2.  Verwendung [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) und [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) Makros mit benutzerdefinierten `CSettingsStore` Klasse, um die dynamische Erstellung zu ermöglichen.  
  
3.  Virtuelle Funktionen überschreiben und Implementieren der `Read` und `Write` Funktionen in Ihre benutzerdefinierte Klasse. Implementieren Sie keine anderen Funktionen zum Lesen und Schreiben von Daten an die gewünschte Position.  
  
4.  Rufen Sie in Ihrer Anwendung `CSettingsStoreSP::SetRuntimeClass` und übergeben Sie einen Zeiger auf die [CRuntimeClass Struktur](../../mfc/reference/cruntimeclass-structure.md) aus der Klasse abgerufen.  
  
 Wenn das Framework in der Regel auf die Registrierung zugreifen würden, wird jetzt dynamisch Ihre benutzerdefinierte Klasse zu instanziieren und verwenden, um die Daten lesen oder schreiben.  
  
 `CSettingsStoreSP::SetRuntimeClass`verwendet eine globale statische Variable. Daher ist nur einen benutzerdefinierter Speicher zu einem Zeitpunkt zur Verfügung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsettingsstore.h  
  
##  <a name="a-namecreatea--csettingsstorespcreate"></a><a name="create"></a>CSettingsStoreSP::Create  
 Erstellt eine neue Instanz eines Objekts, das von abgeleitet ist die [CSettingsStore Klasse](../../mfc/reference/csettingsstore-class.md).  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAdmin`  
 Ein boolescher Parameter, der bestimmt, ob ein `CSettingsStore` -Objekt wird erstellt, im Administratormodus.  
  
 [in] `bReadOnly`  
 Ein boolescher Parameter, der bestimmt, ob ein `CSettingsStore` -Objekt wird erstellt, für die nur-Lese-Zugriff.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das neu erstellte `CSettingsStore` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Methode [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) um zu bestimmen, welche Art von Objekt `CSettingsStoreSP::Create` erstellt. Diese Methode erstellt standardmäßig ein `CSettingsStore` Objekt.  
  
 Wenn Sie erstellen ein `CSettingsStore` -Objekt im Administratormodus, der Standardspeicherort für alle Zugriff auf die Registrierung ist HKEY_LOCAL_MACHINE. Andernfalls ist der Standardspeicherort für alle Zugriff auf die Registrierung HKEY_CURRENT_USER.  
  
 Wenn `bAdmin` ist `TRUE`, die Anwendung muss über Administratorrechte verfügen. Andernfalls schlägt er fehl, wenn er versucht, auf die Registrierung zuzugreifen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CSettingsStoreSP` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp&33;](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="a-namecsettingsstorespa--csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP  
 Erstellt eine [CSettingsStoreSP Klasse](../../mfc/reference/csettingsstoresp-class.md) Objekt.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwUserData`  
 Benutzerdefinierte Daten, die die `CSettingsStoreSP` -Objekt speichert.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSettingsStoreSP` -Objekt speichert die Daten aus `dwUserData` in der geschützten Membervariablen `m_dwUserData`.  
  
##  <a name="a-namesetruntimeclassa--csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass  
 Festlegen der Common Language Runtime-Klasse. Die Methode [CSettingsStoreSP::Create](#create) verwendet die Common Language Runtime-Klasse des zu erstellenden Objekts bestimmen.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRTI`  
 Ein Zeiger auf die Laufzeit-Klasseninformationen für eine Klasse abgeleitet wird, aus der [CSettingsStore Klasse](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Bei Erfolg; `FALSE` durch die Klasse identifiziert `pRTI` stammt nicht von `CSettingsStore`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die [CSettingsStoreSP-Klasse](../../mfc/reference/csettingsstoresp-class.md) von Klassen abgeleitet werden `CSettingsStore`. Verwenden Sie die Methode `SetRuntimeClass` Wenn sollen Objekte eine benutzerdefinierte Klasse erstellen, die von abgeleitet ist `CSettingsStore`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md)

