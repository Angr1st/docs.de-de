---
title: ICorProfilerCallback::RemotingClientInvocationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0cc27bd6a5c0cb85f4822a4481d9588705b71bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575959"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a>ICorProfilerCallback::RemotingClientInvocationStarted-Methode
Benachrichtigt den Profiler, dass ein Remoteaufrufs gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.  
  
 Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:  
  
-   `RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:  
  
-   Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden. Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.  
  
-   Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
