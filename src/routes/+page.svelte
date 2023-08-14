<script lang="ts">
    import { emojiList } from "./emoji";

    type State = 'start' | 'playing' | 'paused' | 'won' | 'lost'

    let state: State = 'start'
    let size = 20
    let grid = createdGrid()
    let maxMatches = grid.length / 2
    let selected: number[] = []
    let matches: string[] = []

    function createdGrid() {
        let cards = new Set<string>()
        let maxSize = size / 2

        while (cards.size < maxSize) {
            const randomIndex = Math.floor(Math.random() * emojiList.length)
            cards.add(emojiList[randomIndex])
        }

        return shuffle([...cards, ...cards])
    }

    function shuffle<Items>(array: Items[]) {
        return array.sort(() => Math.random() - 0.5)
    }

    console.log(grid)
</script>

Hello