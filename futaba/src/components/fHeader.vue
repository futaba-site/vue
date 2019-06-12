<template>
    <div class="fHeader">
        <router-link class="siteLogo" :to="{ name: 'home' }">
            <span class="hasTopWords">双葉<span class="topWords">ふたば</span></span>
            <span>の</span>
            <span class="hasTopWords">魔法笔记<span class="topWords">まほうのほん</span></span>
        </router-link>
        <div class="headerNav">
            <ul>
                <li><router-link :to="{ name: 'home' }"><i class="el-icon-s-home"></i>HOME</router-link></li>
                <li><router-link :to="{ name: 'home' }"><i class="el-icon-s-management"></i>ARCHIVE</router-link></li>
                <li><router-link :to="{ name: 'home' }"><i class="el-icon-s-comment"></i>COMMENT</router-link></li>
                <li><router-link :to="{ name: 'home' }"><i class="el-icon-s-promotion"></i>ABOUT</router-link></li>
            </ul>
        </div>
        <div class="headerOptions">
            <ul>
                <li><i class="el-icon-search"></i></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "fHeader"
}
</script>

<style lang="less">
.fHeader {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 78px;
    margin: 0;
    padding: 0 15px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background-color: #FFFFFF;
}

.siteLogo {
    
    span {
        display: inline-block;
        font-size: 24px;
        font-weight: 600;
    }

    .hasTopWords {
        position: relative;

        .topWords {
            position: absolute;
            top: -10px;
            left: 0;
            font-size: 12px;
            font-size: 300;
        }
    }
}

.headerNav {
    ul {
        margin: 0;
        padding: 0;
        list-style-type: none;
        display: flex;
        flex-direction: row;

        li {
            margin: 0 10px;

            a {
                padding: 5px;
                text-decoration: none;

                i {
                    padding-right: 3px;
                }
            }
        }
    }
}

.headerOptions {
    ul {
        margin: 0;
        padding: 0;
        list-style-type: none;
        display: flex;
        flex-direction: row;

        li {
            i {
                font-size: 24px;
            }
        }
    }
}
</style>

