select          banco.nome,
              agencia.nome,
       conta_corrente.numero,
       conta_corrente.digito,
	      cliente.nome,
   cliente_transacoes.tipo_transacao_id,
       tipo_transacao.nome
from banco
join agencia
         on            agencia.banco_numero      =          banco.numero
join conta_corrente
         on     conta_corrente.banco_numero      =          banco.numero	
        and     conta_corrente.agencia_numero    =        agencia.numero
join cliente
         on            cliente.numero            = conta_corrente.cliente_numero
join cliente_transacoes
         on cliente_transacoes.cliente_numero    =        cliente.numero
join cliente_transacoes
         on cliente_transacoes.tipo_transacao_id = tipo_transacao.id;