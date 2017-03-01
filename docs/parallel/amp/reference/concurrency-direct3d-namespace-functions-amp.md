---
title: 'Concurrency:: Direct3D-Namespace-Funktionen (EVA) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 46cafc3c6d6f21eaf147ef0edfeca7f2c81d64e6
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency:: Direct3D-Namespace-Funktionen (AMP)
||||  
|-|-|-|  
|[ABS-Funktion](#abs)|[Clamp-Funktion](#clamp)|[Countbits-Funktion](#countbits)|
|[Create_accelerator_view-Funktion](#create_accelerator_view)|||
|[d3d_access_lock-Funktion](#d3d_access_lock)|[d3d_access_try_lock-Funktion](#d3d_access_try_lock)|[d3d_access_unlock-Funktion](#d3d_access_unlock)|  
|[Firstbithigh-Funktion](#firstbithigh)|[Firstbitlow-Funktion](#firstbitlow)|[Get_buffer-Funktion](#get_buffer)|  
|[Imax-Funktion](#imax)|[Imin-Funktion](#imin)|[Is_timeout_disabled-Funktion](#is_timeout_disabled)|  
|[MAD-Funktion](#mad)|[Make_array-Funktion](#make_array)|[Noise-Funktion](#noise)|  
|[RADIANS-Funktion](#radians)|[Rcp-Funktion](#rcp)|[Reversebits-Funktion](#reversebits)|  
|[sättigungsfunktion](#saturate)|[Sign-Funktion](#sign)|[Smoothstep-Funktion](#smoothstep)|  
|[Schrittfunktion](#step)|[UMAX-Funktion](#umax)|[Umin-Funktion](#umin)|  
  
##  <a name="a-nameabsa--abs-function"></a><a name="abs"></a>ABS-Funktion  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den absoluten Wert des Arguments zurück.  
  
##  <a name="a-nameclampa--clamp-function"></a><a name="clamp"></a>Clamp-Funktion  
 Berechnet den Wert des angegebenen ersten Arguments, das an einen Bereich gebunden ist, der vom zweiten und dritten angegebenen Argument definiert wird.  
  
```  
inline float clamp(
    float _X,  
    float _Min,  
    float _Max) restrict(amp);

 
inline int clamp(
    int _X,  
    int _Min,  
    int _Max) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Der zu bindende Wert  
  
 `_Min`  
 Die untere Grenze des gebundenen Bereichs.  
  
 `_Max`  
 Die obere Grenze des gebundenen Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 Der gebundene Wert von `_X`.  
  
##  <a name="a-namecountbitsa--countbits-function"></a><a name="countbits"></a>Countbits-Funktion  
 Zählt die Anzahl der festgelegten Bits in _X  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahlwert ohne Vorzeichen  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der festgelegten Bits in _X  

## <a name="a-namecreateacceleratorviewa-createacceleratorview-function"></a><a name="create_accelerator_view"></a>Create_accelerator_view-Funktion
Erstellt ein [Accelerator_view](accelerator-view-class.md) Objekt von einem Zeiger auf eine Direct3D-Geräteschnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
accelerator_view create_accelerator_view(  
    IUnknown * _D3D_device  
    queuing_mode _Qmode = queuing_mode_automatic);  
  
accelerator_view create_accelerator_view(  
    accelerator& _Accelerator,  
    bool _Disable_timeout  
    queuing_mode _Qmode = queuing_mode_automatic);  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Accelerator`  
 Die Zugriffstaste, auf der das neue accelerator_view-Objekt erstellt werden soll.  
  
 `_D3D_device`  
 Der Zeiger auf die Schnittstelle eines Direct3D-Geräts.  
  
 `_Disable_timeout`  
 Ein boolescher Parameter, der angibt, ob das Timeout für das neu erstellte accelerator_view-Objekt deaktiviert werden sollte. Dies entspricht dem D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT-Flag für die Erstellung von Direct3D-Geräten und wird verwendet, um anzugeben, ob das Betriebssystem Arbeitslasten zulässt, deren Ausführung mehr als 2 Sekunden dauert, ohne das Gerät über den Windows-TDR-Mechanismus (Timeout Detection and Recovery) zurückzusetzen. Die Verwendung dieses Flags wird empfohlen, wenn Sie zeitintensive Aufgaben im accelerator_view-Objekt ausführen müssen.  
  
 `_Qmode`  
 Die [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) für das neu erstellte accelerator_view-Objekt verwendet werden soll. Der Standardwert dieses Parameters ist `queuing_mode_automatic`.  
  
## <a name="return-value"></a>Rückgabewert  
 Das `accelerator_view`-Objekt, das über die übergebene Direct3D-Geräteschnittstelle erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt ein neues `accelerator_view`-Objekt von einem vorhandenen Zeiger auf eine Direct3D-Geräteschnittstelle. Wenn der Funktionsaufruf folgt, wird der Verweiszähler des Parameters mit einem `AddRef`-Aufruf der Schnittstelle erhöht. Sie können das Objekt sicher freigeben, wenn es im DirectX-Code nicht mehr benötigt wird. Wenn der Methodenaufruf fehlschlägt, eine [Runtime_exception](runtime-exception-class.md) ausgelöst.  
  
 Das `accelerator_view`-Objekt, das Sie mit dieser Funktion erstellen, ist threadsicher. Sie müssen die gleichzeitige Verwendung des `accelerator_view`-Objekts synchronisieren. Die unsynchronisierte gleichzeitige Verwendung des `accelerator_view`-Objekts und die unformatierte ID3D11Device-Schnittstelle verursachen ein nicht definiertes Verhalten.  
  
 Die C++-AMP-Laufzeit stellt detaillierte Fehlerinformationen im Debugmodus mithilfe der D3D-Debugebene bereit, wenn Sie das `D3D11_CREATE_DEVICE_DEBUG`-Flag verwenden.  
  
  
##  <a name="a-named3daccesslocka--d3daccesslock-function"></a><a name="d3d_access_lock"></a>d3d_access_lock-Funktion  
 Ruft eine Sperre für eine "accelerator_view" ab, um D3D-Vorgänge in Ressourcen, die gemeinsam mit der "accelerator_view" genutzt werden, sicher ausführen zu können. Die "accelerator_view" und alle C++ AMP-Ressourcen, die dieser "accelerator_view" intern zugeordnet sind, werden gesperrt, wenn Vorgänge ausgeführt werden, und blockieren, während ein anderer Thread die D3D-Zugriffssperre inne hat. Diese Sperre ist nicht rekursiv: Es ist nicht definiertes Verhalten, diese Funktion von einem Thread aufzurufen, der bereits die Sperre besitzt. Es ist nicht definiertes Verhalten, Vorgänge für die "accelerator_view" oder Datencontainer auszuführen, die der "accelerator_view" vom Thread zugeordnet sind, der die D3D-Zugriffssperre besitzt. Siehe auch: "scoped_d3d_access_lock", eine RAII-Formatklasse für eine bereichsbasierte D3D-Zugriffssperre.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parameter  
 `_Av`  
 Die zu sperrende "accelerator_view".  
  
##  <a name="a-named3daccesstrylocka--d3daccesstrylock-function"></a><a name="d3d_access_try_lock"></a>d3d_access_try_lock-Funktion  
 Versuch, ohne Blockierung die D3D-Zugriffssperre für eine accelerator_view abzurufen.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parameter  
 `_Av`  
 Die zu sperrende "accelerator_view".  
  
### <a name="return-value"></a>Rückgabewert  
 "true", wenn die Sperre abgerufen wurde, oder "false", wenn sie durch einen anderen Thread verwendet wird.  
  
##  <a name="a-named3daccessunlocka--d3daccessunlock-function"></a><a name="d3d_access_unlock"></a>d3d_access_unlock-Funktion  
 Gibt die D3D-Zugriffssperre für die angegebene accelerator_view frei. Wenn der aufrufende Thread nicht die Sperre für "accelerator_view" hat, sind die Ergebnisse nicht definiert.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parameter  
 `_Av`  
 Die „accelerator_view“, für die die Sperre aufgehoben werden soll.  
  
##  <a name="a-namefirstbithigha--firstbithigh-function"></a><a name="firstbithigh"></a>Firstbithigh-Funktion  
 Ruft den Speicherort des ersten festgelegten Bits in _X ab, beginnend mit dem höchsten Bit und arbeitet sich weiter bis zum niedrigsten Bit.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Der Speicherort des ersten festgelegten Bits  
  
##  <a name="a-namefirstbitlowa--firstbitlow-function"></a><a name="firstbitlow"></a>Firstbitlow-Funktion  
 Ruft den Speicherort des ersten festgelegten Bits in _X ab, beginnend mit dem niederwertigsten Bit und arbeitet sich weiter bis zum höchsten Bit.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Speicherort des ersten festgelegten Bits zurück  
  
##  <a name="a-namegetbuffera--getbuffer-function"></a><a name="get_buffer"></a>Get_buffer-Funktion  
 Rufen Sie die Direct3D-Pufferschnittstelle ab, die dem angegebenen Array zugrunde liegt.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;  
```  
  
### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Typ der Elemente im Array.  
  
 `_Rank`  
 Der Rang des Arrays.  
  
 `_Array`  
 Ein Array auf einem Direct3D-accelerator_view_Objekt, für das die zugrunde liegende Direct3D-Pufferschnittstelle zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der IUnknown-Schnittstellenzeiger entspricht dem Direct3D-Puffer, der dem Array zugrunde liegt.  
  
##  <a name="a-nameimaxa--imax-function"></a><a name="imax"></a>Imax-Funktion  
 Festlegung des höchsten numerischen Werts der Argumente  
  
```  
inline int imax(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des höchsten numerischen Werts der Argumente  
  
##  <a name="a-nameimina--imin-function"></a><a name="imin"></a>Imin-Funktion  
 Festlegung des niedrigsten numerischen Werts der Argumente  
  
```  
inline int imin(
    int _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des niedrigsten numerischen Werts der Argumente  
  
##  <a name="a-nameistimeoutdisableda--istimeoutdisabled-function"></a><a name="is_timeout_disabled"></a>Is_timeout_disabled-Funktion  
 Gibt ein boolesches Flag zurück, das angibt, ob Timeout für die angegebene "accelerator_view" deaktiviert ist. Dies entspricht dem D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT-Flag für Direct3D-Geräteerstellung.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Parameter  
 `_Accelerator_view`  
 Die "accelerator_view", für die die deaktivierte Timeouteinstellung, abgefragt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolesches Flag, das angibt, ob Timeout für die angegebene "accelerator_view" deaktiviert ist.  
  
##  <a name="a-namemada--mad-function"></a><a name="mad"></a>MAD-Funktion  
 Berechnet das Produkt des ersten und zweiten angegebenen Arguments und fügt dann das dritte angegebene Argument hinzu.  
  
```  
inline float mad(
    float _X,  
    float _Y,  
    float _Z) restrict(amp);

 
inline double mad(
    double _X,  
    double _Y,  
    double _Z) restrict(amp);

 
inline int mad(
    int _X,  
    int _Y,  
    int _Z) restrict(amp);

 
inline unsigned int mad(
    unsigned int _X,  
    unsigned int _Y,  
    unsigned int _Z) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Das erste angegebene Argument.  
  
 `_Y`  
 Das zweite angegebene Argument.  
  
 `_Z`  
 Das dritte angegebene Argument.  
  
### <a name="return-value"></a>Rückgabewert  
 The result of `_X` * `_Y` + `_Z`.  
  
##  <a name="a-namemakearraya--makearray-function"></a><a name="make_array"></a>Make_array-Funktion  
 Erstellt ein Array aus dem Schnittstellenzeiger eines Direct3D-Puffers.  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,  
    const Concurrency::accelerator_view& _Rv,  
    IUnknown* _D3D_buffer)  ;  
```  
  
### <a name="parameters"></a>Parameter  
 `value_type`  
 Der Elementtyp des zu erstellenden Arrays.  
  
 `_Rank`  
 Der Rang des zu erstellenden Arrays.  
  
 `_Extent`  
 Ein Wertebereich, der die Form des Arrayaggregats beschreibt.  
  
 `_Rv`  
 Eine D3D-Zugriffstastenansicht, in der das Array erstellt werden soll.  
  
 `_D3D_buffer`  
 IUnknown-Schnittstellenzeiger des D3D-Puffers zum Erstellen des Arrays.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein mithilfe des angegebenen Direct3D-Puffers erstelltes Array.  
  
##  <a name="a-namenoisea--noise-function"></a><a name="noise"></a>Noise-Funktion  
 Generiert einen zufälligen Wert mithilfe des Perlin-Noise-Algorithmus  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert aus dem Perlin-Noise generiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Perlin-Noise-Wert innerhalb eines Bereichs zwischen-1 und 1  
  
##  <a name="a-nameradiansa--radians-function"></a><a name="radians"></a>RADIANS-Funktion  
 Konvertiert _X von Grad in Bogenmaß  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X von Grad in Bogenmaß konvertiert.  
  
##  <a name="a-namercpa--rcp-function"></a><a name="rcp"></a>Rcp-Funktion  
 Berechnet den Kehrwert des angegebenen Arguments mithilfe einer schnellen Näherung.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Der Wert, für den der Kehrwert berechnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Kehrwert des angegebenen Arguments.  
  
##  <a name="a-namereversebitsa--reversebits-function"></a><a name="reversebits"></a>Reversebits-Funktion  
 Kehrt die Reihenfolge der Bits in _X um  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahlwert ohne Vorzeichen  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert in der Reihenfolge der Bit vertauscht _X  
  
##  <a name="a-namesaturatea--saturate-function"></a><a name="saturate"></a>sättigungsfunktion  
 Bindet _X im Bereich zwischen 0 und 1  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X gebunden ist, der innerhalb des Bereichs von 0 bis 1  
  
##  <a name="a-namesigna--sign-function"></a><a name="sign"></a>Sign-Funktion  
 Bestimmt das Vorzeichen des angegebenen Arguments.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Das Vorzeichen des Arguments.  
  
##  <a name="a-namesmoothstepa--smoothstep-function"></a><a name="smoothstep"></a>Smoothstep-Funktion  
 Gibt eine glatte Hermite-Interpolation zwischen 0 und 1 zurück, wenn _X im Bereich [_Min, _Max] liegt.  
  
```  
inline float smoothstep(
    float _Min,  
    float _Max,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Min`  
 Gleitkommawert  
  
 `_Max`  
 Gleitkommawert  
  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn _X _Min unterschreitet. 1, wenn _X _Max größer ist. andernfalls ein Wert zwischen 0 und 1, wenn _X im Bereich [_Min, _Max] liegt.  
  
##  <a name="a-namestepa--step-function"></a><a name="step"></a>Schrittfunktion  
 Vergleicht zwei Werte und gibt, je nachdem welcher Wert größer ist, 0 oder 1 zurück  
  
```  
inline float step(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Y`  
 Gleitkommawert  
  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 1 zurück, wenn die _X größer als oder gleich _Y ist. andernfalls 0  
  
##  <a name="a-nameumaxa--umax-function"></a><a name="umax"></a>UMAX-Funktion  
 Festlegung des höchsten numerischen Werts der Argumente  
  
```  
inline unsigned int umax(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des höchsten numerischen Werts der Argumente  
  
##  <a name="a-nameumina--umin-function"></a><a name="umin"></a>Umin-Funktion  
 Festlegung des niedrigsten numerischen Werts der Argumente  
  
```  
inline unsigned int umin(
    unsigned int _X,  
    unsigned int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des niedrigsten numerischen Werts der Argumente  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: Direct3D-Namespace](concurrency-direct3d-namespace.md)

