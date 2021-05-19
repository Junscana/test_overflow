<template>
  <main class="discograpy">
    <page-title title="discograpy" />
    <div class="page-body">
      <ul class="tune-list">
        <li v-for="(tuneItem, index) in tuneList" :key="index" class="tune-list__item">
          <h2 class="tune-list__item__title">{{ tuneItem.title }}</h2>
          <ul class="tune-list__item__info">
            <li class="tune-list__item__info__item">
              <dl class="tune-list__item__info__item__inner">
                <dt class="tune-list__item__info__item__inner__title">作曲</dt>
                <dd class="tune-list__item__info__item__inner__content">{{ tuneItem.composer }}</dd>
              </dl>
            </li>
            <li class="tune-list__item__info__item">
              <dl class="tune-list__item__info__item__inner">
                <dt class="tune-list__item__info__item__inner__title">作詞</dt>
                <dd class="tune-list__item__info__item__inner__content">{{ tuneItem.lyricist }}</dd>
              </dl>
            </li>
          </ul>
          <button class="tune-list__item__modal-btn help_link__button" @click="changeLyric(tuneItem.lyrics), openModal()">
            歌詞を見る
          </button>
        </li>
      </ul>
    </div>
    <Modal v-if="modalFlag" @close-modal="closeModal" >
      <div style="white-space:pre-wrap;">{{ lyrics }}</div>
    </Modal>
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
export default {
  data () {
    return {
      modalFlag: false,
      lyrics: '',
      breadcrumbs: [
        {
          name: 'home',
          path: '/'
        },
        {
          name: 'discograpy',
          path: ''
        }
      ],
      tuneList: [
        {
          title: '楽曲タイトル１',
          composer: 'テキスト',
          lyricist: 'テキスト',
          lyrics: 'ブンブンブン  ブンブンブン\nブンブンブン  ブンブンブン\nインフルエンサー\n(HEY！HEY！HEY！)\nブンブンブン  ブンブンブン\nブンブンブン  ブンブンブン\nインフルエンサー\n(HEY！HEY！HEY！)\n\nいつだって  知らないうちに\n僕は見まわしている(何度も)\n君がどこで何をしているか\n気になってしまうんだ\n(落ち着かなくなる)\n\n声くらい掛ければいい\n誰もが思うだろう(できない)\n君がいる場所がわかったら\n僕には地図になるんだ\n\n気配以上  会話未満\n恋はいつも余所余所(よそよそ)しい\n胸騒ぎが聴こえないように\n世界から言葉なんか\n消えてしまえばいい\n\n地球と太陽みたいに\n光と影が生まれて\n君を探してばかり\n距離は縮まらない\n(HEY！HEY！HEY！)\n重力  引力  惹かれて\n1から10まで君次第\n存在するだけで\n影響  与えてる\nインフルエンサー\n\nブンブンブン  ブンブンブン\nブンブンブン  ブンブンブン\nインフルエンサー\n(HEY！HEY！HEY！)\n\nその他(ほか)の誰かなんて\n全然  興味ないけど(なぜだか)\n君が何を考えてるか\n知りたくてしょうがない\n(振り回されてる)\n\nミュージックやファッションとか\n映画や小説とか(何でも)\nお気に入りのもの  手にすれば\n時間を共有できるんだ\n\n外見よりももっと深く\n恋は内面  覗くことさ\n君らしさに溺れてしまう\n切なさがもの足りない\n僕は叫んでいる\n\n自転と公転みたいに\n意識と愛が回って\n君を想い続ける\n宇宙の中心さ\n(HEY！HEY！HEY！)\nどんなに離れていたって\n働き掛けるその力\nもし君がいなくなったら\n僕は僕じゃなくなる\nインフルエンサー\n\n地球と太陽みたいに\n光と影が生まれて\n君を探してばかり\n距離は縮まらない\n(HEY！HEY！HEY！)\n重力  引力  惹かれて\n1から10まで君次第\n存在するだけで\n影響  与えてる\nインフルエンサー\n\nブンブンブン  ブンブンブン\nブンブンブン  ブンブンブン\nインフルエンサー\n(HEY！HEY！HEY！)\nブンブンブン  ブンブンブン\nブンブンブン  ブンブンブン\nインフルエンサー\n(HEY！HEY！HEY！)'
        },
        {
          title: '楽曲タイトル２',
          composer: 'テキスト',
          lyricist: 'テキスト',
          lyrics: "Hang in there！ Come on, keep at it！\nWOW WOW WOW WOW\nHang in there！ I believe in you！\nWOW WOW WOW WOW\nHang in there！ Make a run for it！\nWOW WOW WOW WOW\nHang in there！ Don't you dare give up！\nWOW WOW WOW WOW\n\n夜を走り抜けてく\nヘッドライトの残像\n目に映ったすべては\nどうせ一瞬の幻なんだ\n\nやがて夢も覚めるなら\n今のためにもがこう\nカッコつけて生きてても\nいつかきっと悔いが残る\n\n他人(ひと)の目　気にして\n生きていたってしょうがないよ\n\nいつかの場所から\nWOW WOW WOW WOW\n歩き出せばいい\nWOW WOW WOW WOW\n\n誰も変われるんだ\nWOW WOW WOW WOW\n人は進化する\nWOW WOW WOW WOW\nやがて過去を忘れ\nWOW WOW WOW WOW\nそして明日(あす)を生きる\nWOW WOW WOW WOW\n\nあの日　眺めていたのは\nショウウィンドウの未来さ\n本物が欲しいのなら\n自分の手で掴むしかない\n\n坂のない人生は\n汗の輝きを知らない\n\nYou can do it！ 君ならば\nWOW WOW WOW WOW\nYou can do it！ できるはずだ\nWOW WOW WOW WOW\n\nHang in there！ Come on, keep at it！\nWOW WOW WOW WOW\nHang in there！ I believe in you！\nWOW WOW WOW WOW\nHang in there！ Make a run for it！\nWOW WOW WOW WOW\nHang in there！ Don't you dare give up！\nWOW WOW WOW WOW\n\nWhy are you going there? Say\nWOW WOW WOW WOW\nNo one can stop you, no way\nWOW WOW WOW WOW\n\nWhy are you going there? Say\nWOW WOW WOW WOW\nYes, I'm on your side, always\nWOW WOW WOW WOW\n\nHang in there！ この通りで\nWOW WOW WOW WOW\nHang in there！ 誓ったことを\nWOW WOW WOW WOW\nHang in there！ 歩きながら\nWOW WOW WOW WOW\nHang in there！ 思い出すよ\nWOW WOW WOW WOW"
        },
        {
          title: '楽曲タイトル３',
          composer: 'テキスト',
          lyricist: 'テキスト',
          lyrics: '電車が近づく\n気配が好きなんだ\n高架線のその下で耳を澄ましてた\n\n柱の落書き\n数字とイニシャルは\n誰が誰に何を残そうとしたのだろう\n\n歳月(とき)の流れは(歳月(とき)の流れは)\n教えてくれる(教えてくれる)\n過ぎ去った普通の日々が\nかけがえのない足跡と…\n\nサヨナラに強くなれ\nこの出会いに意味がある\n悲しみの先に続く\n僕たちの未来\n始まりはいつだって\nそう何かが終わること\nもう一度君を抱きしめて\n守りたかった\n愛に代わるもの\n\n電車が通過する\n轟音(ごうおん)と風の中\n君の唇が動いたけど\n聴こえない\n\n静寂が戻り\n答えを待つ君に\n僕は目を見て微笑みながら\n頷いた\n\n大切なもの(大切なもの)\n遠ざかっても(遠ざかっても)\n新しい出会いがまた\nいつかはきっとやって来る\n\nサヨナラを振り向くな\n追いかけてもしょうがない\n思い出は\n今いる場所に置いて行こうよ\n終わることためらって\n人は皆立ち止まるけど\n僕たちは抱き合ってた\n腕を離して\nもっと強くなる\n\n躊躇してた間に\n陽は沈む(切なく)\n遠くに見える鉄塔\nぼやけてく(確かな距離)\n君が好きだけど(君が好きだけど)\nちゃんと言わなくちゃいけない\n見つめあった瞳が星空になる\n\nサヨナラは通過点\nこれからだって何度もある\n後ろ手(で)でピースしながら\n歩き出せるだろう\n君らしく…\n\nサヨナラに強くなれ\nこの出会いに意味がある\n悲しみの先に続く\n僕たちの未来\n始まりはいつだって\nそう何かが終わること\nもう一度君を抱きしめて\n本当の気持ち問いかけた\n失いたくない\n守りたかった\n愛に代わるもの'
        }
      ]
    }
  },
  methods: {
    openModal () {
      this.modalFlag = true
    },
    closeModal () {
      this.modalFlag = false
    },
    changeLyric (lyrics) {
      this.lyrics = lyrics
    }
  }
}
</script>

<style lang="scss" scoped>
.page-body {
  margin-top: 4rem;
}

.tune-list {
  padding: 0 1.5rem;
}

.tune-list__item {
  margin-top: 2rem;

  &:first-of-type {
    margin-top: 0;
  }
}

.tune-list__item__title {
  font-size: 1.8rem;

  &::before {
    content: '○';
    margin-right: 0.6rem;
  }
}

.tune-list__item__info {
  display: flex;
  margin-top: 1rem;

  &__item {
    margin-left: 2rem;

    &:first-of-type {
      margin-left: 0;
    }
  }
}

.tune-list__item__info__item__inner {
  display: flex;

  &__title {
    font-size: 1.4rem;
  }

  &__title::after {
    content: '：';
    margin-right: 0.4rem;
  }

  &__content {
    font-size: 1.4rem;
  }
}

.tune-list__item__modal-btn {
  display: block;
  margin: 2rem auto auto auto;
}
</style>
