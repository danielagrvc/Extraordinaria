import random
class Armaduras:
    def _init_(self):
        self.legiones = ['FL', 'TF', 'TK', 'CT', 'FN', 'FO']
        self.codigo
        self.tabla_hash1 = {}
        self.tabla_hash2 = {}
        self.armaduras = []

    def generar_armaduras(self):
        for i in range(2000):
            legión = random.choice(self.legiones)
            codigo = legión + '-'
            for j in range(4):
                codigo += str(random.randint(0, 9))
            armadura = Armaduras()
            armadura.codigo(codigo)
            self.armaduras.append(armadura)

    def cargar_armaduras(self):
        for armadura in self.armaduras:
            ultimos_digitos = armadura.codigo[-3:]
            if ultimos_digitos not in self.tabla_hash1:
                self.tabla_hash1[ultimos_digitos] = []
            self.tabla_hash1[ultimos_digitos].append(armadura)

            inicial_legion = armadura.codigo[:2]
            if inicial_legion not in self.tabla_hash2:
                self.tabla_hash2[inicial_legion] = []
            self.tabla_hash2[inicial_legion].append(armadura)

    def eliminar_armadura(self, codigo):
        for armadura in self.armaduras:
            if armadura.codigo == codigo:
                self.tabla_hash1[armadura.codigo[-3:]].remove(armadura)
                self.tabla_hash2[armadura.codigo[:2]].remove(armadura)
                self.armaduras.remove(armadura)
                return True
        return False

    def obtener_armaduras_por_digitos(self, digitos):
        if digitos in self.tabla_hash1:
            return self.tabla_hash1[digitos]
        else:
            return []

    def obtener_armaduras_por_legion(self, legion):
        if legion in self.tabla_hash2:
            return self.tabla_hash2[legion]
        else:
            return []

    def asignar_mision(self, digitos, mision):
        armadura_digitos = self.obtener_armaduras_por_digitos(digitos)
        for stormtrooper in armadura_digitos:
            stormtrooper.asignar_mision(mision)