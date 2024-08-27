# Trilha Python DIO
class ContaBancaria:
    def __init__(self, numero_conta, titular, saldo=0):
        self.numero_conta = numero_conta
        self.titular = titular
        self.saldo = saldo
        self.extrato = []

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            self.extrato.append(f"Depósito: R$ {valor:.2f}")
        else:
            print("Valor inválido para depósito.")

    def sacar(self, valor):
        if 0 < valor <= self.saldo:
            self.saldo -= valor
            self.extrato.append(f"Saque: R$ {valor:.2f}")
        else:
            print("Saldo insuficiente ou valor inválido para saque.")

    def extrato(self):
        print("\n=== Extrato da Conta ===")
        for transacao in self.extrato:
            print(transacao)
        print(f"Saldo atual: R$ {self.saldo:.2f}")

# Criando uma conta
conta1 = ContaBancaria(12345, "João da Silva", 1000)

# Realizando operações
conta1.depositar(500)
conta1.sacar(200)
conta1.extrato()
