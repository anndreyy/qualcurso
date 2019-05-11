<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2 @click="open_search(curso)">{{ curso }}</h2>
    <div class="next"  @click="return_sort">
      <button>Proximo</button>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'Qual o curso?',
  props: {
    msg: String
  },
  data: () => ({		
    cursos: [
      "Administração - Bacharelado",
      "Agronomia - Bacharelado",
      "Arqueologia - Bacharelado",
      "Arquitetura e Urbanismo - Bacharelado",
      "Artes Visuais - Bacharelado",
      "Artes Visuais - Licenciatura",
      "Biblioteconomia - Bacharelado",
      "Biomedicina - Bacharelado",
      "Ciência da Computação - Bacharelado",
      "Ciências Biológicas - Bacharelado",
      "Ciências Biológicas - Licenciatura",
      "Ciências Atuariais - Bacharelado",
      "Ciências Contábeis - Bacharelado",
      "Ciências Econômicas - Bacharelado",
      "Ciências Naturais - Licenciatura",
      "Ciências Sociais - Bacharelado",
      "Ciências Sociais - Licenciatura",
      "Cinema e Audiovisual - Bacharelado",
      "Dança - Bacharelado",
      "Dança - Licenciatura",
      "Design - Bacharelado",
      "Direito - Bacharelado",
      "Educação Física - Bacharelado",
      "Educação Física - Licenciatura",
      "Enfermagem - Bacharelado",
      "Engenharia Aeronáutica - Bacharelado",
      "Engenharia Agrícola - Bacharelado",
      "Engenharia Ambiental e Sanitária - Bacharelado",
      "Engenharia Cartográfica e de Agrimensura - Bacharelado",
      "Engenharia Civil - Bacharelado",
      "Engenharia de Alimentos - Bacharelado",
      "Engenharia de Bioprocessos - Bacharelado",
      "Engenharia de Computação - Bacharelado",
      "Engenharia de Controle e Automação - Bacharelado",
      "Engenharia de Fortificação e Construção - Bacharelado (oferta exclusiva das Forças Armadas)",
      "Engenharia de Materiais - Bacharelado",
      "Engenharia de Minas - Bacharelado",
      "Engenharia de Pesca - Bacharelado",
      "Engenharia de Petróleo - Bacharelado",
      "Engenharia de Produção - Bacharelado",
      "Engenharia de Telecomunicações - Bacharelado",
      "Engenharia Elétrica - Bacharelado",
      "Engenharia Eletrônica - Bacharelado",
      "Engenharia Florestal - Bacharelado",
      "Engenharia Mecânica - Bacharelado",
      "Engenharia Mecânica de Armamentos - Bacharelado (oferta exclusiva das Forças Armadas)",
      "Engenharia Mecânica de Veículos Militares - Bacharelado (oferta exclusiva das Forças Armadas)",
      "Engenharia Metalúrgica - Bacharelado",
      "Engenharia Naval - Bacharelado",
      "Engenharia Química - Bacharelado",
      "Engenharia Têxtil - Bacharelado",
      "Estatística - Bacharelado",
      "Farmácia - Bacharelado",
      "Filosofia - Bacharelado",
      "Filosofia - Licenciatura",
      "Física - Bacharelado",
      "Física - Licenciatura",
      "Fisioterapia - Bacharelado",
      "Fonoaudiologia - Bacharelado",
      "Geografia - Licenciatura",
      "Geografia - Bacharelado",
      "Geologia - Bacharelado",
      "História - Bacharelado",
      "História - Licenciatura",
      "Informática - Licenciatura",
      "Jornalismo - Bacharelado",
      "Letras - Língua Estrangeira - Bacharelado",
      "Letras - Língua Portuguesa - Bacharelado",
      "Letras - Língua Estrangeira - Licenciatura",
      "Letras - Língua Portuguesa - Licenciatura",
      "Matemática - Bacharelado",
      "Matemática - Licenciatura",
      "Medicina - Bacharelado",
      "Medicina Veterinária - Bacharelado",
      "Meteorologia - Bacharelado",
      "Museologia - Bacharelado",
      "Música - Bacharelado",
      "Música - Licenciatura",
      "Nutrição - Bacharelado",
      "Odontologia - Bacharelado",
      "Pedagogia - Licenciatura",
      "Psicologia - Bacharelado",
      "Publicidade e Propaganda - Bacharelado",
      "Química - Bacharelado",
      "Química - Licenciatura",
      "Radio, TV, Internet (Comunicação Audiovisual e Multimídia) - Bacharelado",
      "Relações Internacionais - Bacharelado",
      "Relações Públicas - Bacharelado",
      "Secretariado Executivo - Bacharelado",
      "Serviço Social - Bacharelado",
      "Sistemas da Informação - Bacharelado",
      "Teatro - Bacharelado",
      "Teatro - Licenciatura",
      "Teologia - Bacharelado",
      "Terapia Ocupacional - Bacharelado",
      "Turismo - Bacharelado",
      "Zootecnia - Bacharelado",
      "Tecnologias",
      "Agrimensura",
      "Agroecologia",
      "Agroindústria",
      "Análise e Desenvolvimento de Sistemas",
      "Aquacultura",
      "Automação Industrial",
      "Biocombustíveis",
      "Biotecnologia",
      "Cafeicultura",
      "Ciência dos Alimentos",
      "Ciências Aeronáuticas",
      "Ciência dos materiais",
      "Comércio Exterior",
      "Construção de Edifícios",
      "Construção de Estradas",
      "Construção Naval",
      "Cooperativismo",
      "Cosmetologia",
      "Design de Jogos Digitais",
      "Design de produto",
      "Design gráfico",
      "Drenagem e Irrigação",
      "Energias Renováveis",
      "Enologia",
      "Esporte e Lazer",
      "Eventos",
      "Fotografia",
      "Fruticultura",
      "Gestão Comercial",
      "Gestão da Qualidade",
      "Gestão da Tecnologia da Informação",
      "Gestão de Petróleo e Gás",
      "Gestão de Recursos Hídricos",
      "Gestão de Segurança Privada",
      "Gestão do Agronegócio",
      "Gestão em Serviços Jurídicos e Notariais",
      "Gestão Financeira",
      "Gestão Hospitalar",
      "Gestão Portuária",
      "Horticultura",
      "Logística",
      "Manutenção Industrial",
      "Mecatrônica e Mecânica de Precisão",
      "Meliponicultura",
      "Mercadologia",
      "Mineração",
      "Negócios Imobiliários",
      "Oftálmica",
      "Processamento de Dados",
      "Processos Escolares",
      "Processos Metalúrgicos",
      "Produção de Aguardente[2]",
      "Produção de Laticínios",
      "Produção de Materiais Plásticos",
      "Produção Fonográfica",
      "Produção Sucroalcooeira",
      "Produção Têxtil",
      "Projetos de Estruturas Aeronáuticas[3]",
      "Radiologia",
      "Recursos Humanos",
      "Redes de Computadores",
      "Redes de Telecomunicações",
      "Saneamento Ambiental",
      "Secretariado",
      "Segurança da Informação",
      "Segurança no Trabalho",
      "Silvicultura",
      "Sistemas de Navegação Fluvial",
      "Sistemas Biomédicos",
      "Sistemas Elétricos",
      "Sistemas Embarcados",
      "Sistemas para Internet",
      "Telemática",
      "Transporte Aéreo"
    ],
    curso: ""
  }),
  methods:{
    return_sort: function (){
      this.curso = this.cursos[Math.floor(Math.random() * this.cursos.length)];
    },
    open_search: function(sort){      
      const url = "https://www.google.com/search?q=" + sort;
      var win = window.open(url, '_blank');
      win.focus();
    }
  },
  created: function(){
		this.return_sort();
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
  h2{
    cursor: pointer;
    font-size: 40px;
  }
  button{
    background: #cc1f41;
    color: #ffffff;
    font-size: 23px;
    border: 0;
    padding: 5px;
    width: 100%;
    height: 100%;
  
  
  }
  .next{
    height: 55px;
    cursor: pointer;
    width: 100%;
    position: fixed;
    left: 0;
    bottom: 0;
    background: #cc1f41;
  }
</style>
