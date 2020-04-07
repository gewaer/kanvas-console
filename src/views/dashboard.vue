<template>
    <div class="dashboard">
        <h4 class="section-title p-l-10">
            Dashboard
        </h4>
        <div class="row align-items-center mb-5">
            <div class="col-12 col-xl-3 mb-4 mb-xl-0">
                <h1 class="title mb-0">
                    Project Overview
                </h1>
            </div>
            <div class="col-12 col-xl">
                <div class="row">
                    <div class="col-12 col-md mb-4 mb-md-0">
                        <div :class="allAppsConected ? 'all-apps-onnected' : 'reconnect-apps'" class="apps-status h-100">
                            <span>{{ allAppsConected ? 'All Apps connected' : 'Reconnect Apps' }}</span>
                            <i class="fas" />
                        </div>
                    </div>
                    <div class="col-12 col-md mb-4 mb-md-0">
                        <div class="get-your-keys card h-100">
                            <span>Get your Keys</span>
                            <i class="fas fa-key" />
                        </div>
                    </div>
                    <div class="col-12 col-md-5 col-xl">
                        <div class="download-sdk">
                            <div class="row mb-3">
                                <div class="col-12 col-xl">
                                    <span class="download-sdk-title">Download SDK</span>
                                </div>
                                <div class="col-12 col-xl-auto text-right">
                                    <a class="get-other-downloads d-flex align-items-center" href="#">
                                        Get other downloads
                                        <i class="ml-2 fas fa-download" />
                                    </a>
                                </div>
                            </div>
                            <div class="row download-sdk-links">
                                <div class="col mb-2">
                                    <button class="btn">
                                        Web
                                    </button>
                                </div>
                                <div class="col mb-2">
                                    <button class="btn">
                                        Mobile
                                    </button>
                                </div>
                                <div class="col mb-2">
                                    <button class="btn">
                                        CLI
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mb-4">
            <div class="d-flex align-items-center col-12 col-lg mb-3 mb-lg-0">
                <span class="mr-3">Filters</span>
                <multiselect
                    :options="['Option 1', 'Option 2']"
                    :multiple="true"
                    :show-labels="false"
                />
            </div>
            <div class="col-auto mb-3 mb-lg-0">
                <button
                    class="btn btn-primary"
                >
                    Add apps
                    <i class="ml-2 fas fa-link" />
                </button>
            </div>
            <div class="col-auto mb-3 mb-lg-0">
                <button
                    class="btn btn-primary"
                >
                    Browse companies
                    <i class="ml-2 fas fa-building" />
                </button>
            </div>
            <div class="d-flex align-items-center col-auto mb-3 mb-lg-0">
                <multiselect
                    v-model="dropdown"
                    :options="['Last 6 Months', 'Option 1', 'Option 2' ]"
                    :show-labels="false"
                    :allow-empty="false"
                    class="time-back-picker"
                >
                    <template slot="singleLabel" slot-scope="props">
                        <i class="mr-2 fas fa-calendar-alt" />
                        <span class="option__title">{{ props.option }}</span>
                    </template>
                </multiselect>
            </div>
        </div>
        <div class="row">
            <div class="col-12 col-xl-4">
                <div class="card">
                    <div class="card-title">
                        Top Apps by signups
                    </div>
                    <div class="card-body">
                        <div class="table-responsive">
                            <table class="table">
                                <tbody>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                App 1
                                            </span>
                                        </td>
                                        <td>
                                            <span class="ascendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                App 2
                                            </span>
                                        </td>
                                        <td>
                                            <span class="descendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
                <div class="card">
                    <div class="card-title">
                        Daily user engagement
                        <span class="ascendant">
                            246K
                        </span>
                    </div>
                    <div class="daily-user-engagement mb-4">
                        <la-cartesian
                            autoresize
                            :height="100"
                            :bound="[0, 25000]"
                            :data="dailyUserEngagement"
                            :padding="0"
                            text-color="#c1c1c5"
                        >
                            <la-line
                                :color="$store.state.Application.settings.settings.secondary_color"
                                :width="3"
                                animated
                                prop="solid"
                            />
                            <la-line
                                :color="$store.state.Application.settings.settings.secondary_color"
                                :width="1"
                                animated
                                dashed="5 7"
                                prop="dashed"
                            />
                            <la-x-axis
                                :font-size="12"
                                prop="name"
                                :interval="30"
                            />
                        </la-cartesian>
                        <div class="line line-1" />
                        <div class="line line-2" />
                        <div class="line line-3" />
                    </div>
                    <div class="card-title">
                        Companies engagement
                    </div>
                    <div class="card-body">
                        <div class="table-responsive">
                            <table class="table">
                                <tbody>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                Company Name
                                            </span>
                                        </td>
                                        <td>
                                            <span>4.96%</span>
                                            <span class="ascendant">
                                                13.8%
                                            </span>
                                        </td>
                                        <td>
                                            <span>0m 05s</span>
                                            <span class="descendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                Company Name
                                            </span>
                                        </td>
                                        <td>
                                            <span>4.96%</span>
                                            <span class="ascendant">
                                                13.8%
                                            </span>
                                        </td>
                                        <td>
                                            <span>0m 05s</span>
                                            <span class="descendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                Company Name
                                            </span>
                                        </td>
                                        <td>
                                            <span>4.96%</span>
                                            <span class="ascendant">
                                                13.8%
                                            </span>
                                        </td>
                                        <td>
                                            <span>0m 05s</span>
                                            <span class="descendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <span class="td-title">
                                                Company Name
                                            </span>
                                        </td>
                                        <td>
                                            <span>4.96%</span>
                                            <span class="ascendant">
                                                13.8%
                                            </span>
                                        </td>
                                        <td>
                                            <span>0m 05s</span>
                                            <span class="descendant">
                                                13.8%
                                            </span>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-12 col-xl-8">
                <div class="statistics">
                    <div class="card">
                        <div class="title">
                            <i class="far fa-chart-bar" />
                            Statistics
                        </div>

                        <div class="card-title">
                            Companies signup
                        </div>
                        <div class="total-and-percentage">
                            <span class="total">246K</span>
                            <span class="percentage">
                                <i class="fas fa-long-arrow-alt-down" />
                                13.8%
                            </span>
                        </div>
                        <la-cartesian
                            class="companies-signup mb-4"
                            :narrow="8"
                            autoresize
                            :height="300"
                            :bound="[0, 25000]"
                            :data="companiesSignups"
                            :padding="0"
                            text-color="#c1c1c5"
                        >
                            <la-bar
                                prop="bar"
                                animated
                                color="#f0f2f8"
                                :width="15"
                            />
                            <la-line
                                :color="$store.state.Application.settings.settings.base_color"
                                :width="2"
                                curve
                                animated
                                prop="area"
                            />
                            <la-x-axis
                                :font-size="12"
                                prop="name"
                                :interval="30"
                                gridline
                                :gridline-interval="5"
                            />
                            <la-y-axis
                                :font-size="12"
                                :format="(value) => `$${value/1000}k`"
                                :ticks="[5000, 10000, 15000, 20000, 25000]"
                                gridline
                                :gridline-interval="5"
                            />
                        </la-cartesian>

                        <div class="card-title">
                            Online users
                        </div>
                        <div class="total-and-percentage">
                            <span class="total">246K</span>
                            <span class="percentage">
                                <i class="fas fa-long-arrow-alt-down" />
                                13.8%
                            </span>
                        </div>
                        <la-cartesian
                            autoresize
                            text-color="#c1c1c5"
                            narrow
                            stacked
                            :height="300"
                            :padding="5"
                            :bound="[-8000, 9000]"
                            :data="onlineUsers"
                        >
                            <la-bar
                                animated
                                :color="$store.state.Application.settings.settings.base_color"
                                :width="60"
                                prop="positive"
                            />
                            <la-bar
                                animated
                                color="#edecfe"
                                :width="60"
                                prop="negative"
                            />
                            <la-x-axis :font-size="12" prop="name" />
                            <la-y-axis :font-size="12" gridline :format="(value) => `$${value/1000}k`" />
                        </la-cartesian>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { Cartesian, Line, Bar, XAxis, YAxis } from "laue";

export default {
    name: "Home",
    components: {
        LaCartesian: Cartesian,
        LaLine: Line,
        LaBar: Bar,
        LaXAxis: XAxis,
        LaYAxis: YAxis
    },
    data() {
        return {
            dropdown: "Last 6 Months",
            allAppsConected: true,
            dailyUserEngagement: [
                { name: "Nov 10, 2017", solid: 11000, dashed: 9000 },
                { name: "Nov 11, 2017", solid: 12000, dashed: 13000 },
                { name: "Nov 12, 2017", solid: 13000, dashed: 16000 },
                { name: "Nov 13, 2017", solid: 14000, dashed: 14500 },
                { name: "Nov 14, 2017", solid: 15000, dashed: 12000 },
                { name: "Nov 15, 2017", solid: 15000, dashed: 14000 },
                { name: "Nov 16, 2017", solid: 14500, dashed: 15000 },
                { name: "Nov 17, 2017", solid: 14000, dashed: 16000 },
                { name: "Nov 18, 2017", solid: 13500, dashed: 16500 },
                { name: "Nov 19, 2017", solid: 13000, dashed: 17000 },
                { name: "Nov 20, 2017", solid: 13200, dashed: 17500 },
                { name: "Nov 21, 2017", solid: 13000, dashed: 16000 },
                { name: "Nov 22, 2017", solid: 13700, dashed: 15000 },
                { name: "Nov 23, 2017", solid: 14000, dashed: 14000 },
                { name: "Nov 24, 2017", solid: 15000, dashed: 13000 },
                { name: "Nov 25, 2017", solid: 15500, dashed: 12000 },
                { name: "Nov 26, 2017", solid: 16500, dashed: 13000 },
                { name: "Nov 27, 2017", solid: 17000, dashed: 14000 },
                { name: "Nov 28, 2017", solid: 14000, dashed: 16000 },
                { name: "Nov 29, 2017", solid: 13000, dashed: 17000 },
                { name: "Nov 30, 2017", solid: 12000, dashed: 17500 },
                { name: "Dic 01, 2017", solid: 11000, dashed: 16000 },
                { name: "Dic 02, 2017", solid: 13000, dashed: 15000 },
                { name: "Dic 03, 2017", solid: 14000, dashed: 14000 },
                { name: "Dic 04, 2017", solid: 15000, dashed: 13000 },
                { name: "Dic 05, 2017", solid: 15500, dashed: 12000 },
                { name: "Dic 06, 2017", solid: 16500, dashed: 13000 },
                { name: "Dic 07, 2017", solid: 15000, dashed: 12000 },
                { name: "Dic 08, 2017", solid: 14000, dashed: 13000 },
                { name: "Dic 09, 2017", solid: 14500, dashed: 13500 },
                { name: "Dic 10, 2017", solid: 15000, dashed: 13500 }
            ],
            companiesSignups: [
                { name: "Nov 10, 2017", area: 5500, bar: 3500 },
                { name: "Nov 11, 2017", area: 13500, bar: 10500 },
                { name: "Nov 12, 2017", area: 11500, bar: 12500 },
                { name: "Nov 13, 2017", area: 15100, bar: 8100 },
                { name: "Nov 14, 2017", area: 9500, bar: 12000 },
                { name: "Nov 15, 2017", area: 14500, bar: 20500 },
                { name: "Nov 16, 2017", area: 12500, bar: 17500 },
                { name: "Nov 17, 2017", area: 15500, bar: 9500 },
                { name: "Nov 18, 2017", area: 10500, bar: 5500 },
                { name: "Nov 19, 2017", area: 13500, bar: 9500 },
                { name: "Nov 20, 2017", area: 10000, bar: 15000 },
                { name: "Nov 21, 2017", area: 15000, bar: 10000 },
                { name: "Nov 22, 2017", area: 10000, bar: 12000 },
                { name: "Nov 23, 2017", area: 13000, bar: 10000 },
                { name: "Nov 24, 2017", area: 10000, bar: 16000 },
                { name: "Nov 25, 2017", area: 12500, bar: 11500 },
                { name: "Nov 26, 2017", area: 5000, bar: 7000 },
                { name: "Nov 27, 2017", area: 10000, bar: 9000 },
                { name: "Nov 28, 2017", area: 9500, bar: 12500 },
                { name: "Nov 29, 2017", area: 11000, bar: 13000 },
                { name: "Nov 30, 2017", area: 14000, bar: 10000 },
                { name: "Dic 01, 2017", area: 10000, bar: 17000 },
                { name: "Dic 02, 2017", area: 9000, bar: 6000 },
                { name: "Dic 03, 2017", area: 13000, bar: 19000 },
                { name: "Dic 04, 2017", area: 17000, bar: 11000 },
                { name: "Dic 05, 2017", area: 12000, bar: 17000 },
                { name: "Dic 06, 2017", area: 10000, bar: 9000 },
                { name: "Dic 07, 2017", area: 6000, bar: 9000 },
                { name: "Dic 08, 2017", area: 10000, bar: 13000 },
                { name: "Dic 09, 2017", area: 14000, bar: 11000 },
                { name: "Dic 10, 2017", area: 12000, bar: 9000 }
            ],
            onlineUsers: [
                { name: "Jan", positive: 8500, negative: 0 },
                { name: "Feb", positive: 5200, negative: 0 },
                { name: "Mar", positive: 2000, negative: -4800 },
                { name: "Apr", positive: 4800, negative: -7600 },
                { name: "May", positive: 8200, negative: -5200 },
                { name: "Jun", positive: 4800, negative: -1800 },
                { name: "Jul", positive: 7000, negative: -4900 }
            ]
        };
    }
};
</script>

<style lang="scss">
.dashboard {
    .multiselect {
        .multiselect__tags {
            min-height: 39px;
            padding-left: 14px;
            padding-top: 9px;
        }
    }

    .time-back-picker {
        width: 200px;
    }

    .apps-status {
        color: white;
        font-size: 20px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 15px;
        border-radius: 5px;
        font-weight: 600;
        box-shadow: 0 7px 14px rgba(132, 132, 132, 0.15);
        min-height: 95px;

        i.fas {
            font-size: 35px;
        }

        &.all-apps-onnected {
            background-color: var(--secondary-color);

            i.fas {
                &::before {
                    content: "\f058";
                }
            }
        }

        &.reconnect-apps {
            background-color: $error-color;

            i.fas {
                &::before {
                    content: "\f071";
                }
            }
        }
    }

    .get-your-keys {
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-direction: row;
        color: var(--secondary-color);
        font-size: 20px;
        min-height: 95px;

        i.fas {
            font-size: 35px;
        }
    }

    .download-sdk {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 100%;
        font-family: "Roboto", sans-serif;
        letter-spacing: .5px;
        border-left: 1px solid #b3c1cb;
        padding-left: 30px;

        @media(max-width: 767px) {
            border-left: 0;
            padding-left: 10px;
        }

        &-title {
            color: #b3c1cb;
            font-size: 18px;
        }

        .get-other-downloads {
            color: var(--secondary-color);
            font-size: 18px;
            text-decoration: none;
        }

        &-links {
            display: flex;
            align-items: center;
            /* height: 100%; */

            button {
                padding: 8px 20px;
                background-color: white;
                width: 100%;
                font-size: 18px;
                color: black;
                border-radius: 50px;
                box-shadow: 0 7px 14px rgba(132, 132, 132, 0.15);
                border: 0;
                font-weight: 500;
                letter-spacing: .5px;

                &:focus {
                    outline: none;
                }
            }
        }
    }

    .statistics {
        .title {
            color: #4d4f5c;
            font-size: 20px;
            font-family: "Roboto", sans-serif;
        }

        .total-and-percentage {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;

            .total {
                font-family: "Roboto", sans-serif;
                font-size: 25px;
                font-weight: 900;
            }

            .percentage {
                color: $error-color;
                font-weight: 700;
                font-size: 14px;
            }
        }

        text {
            font-family: "Roboto", sans-serif;
            fill: #c1c1c5;
        }
    }

    .daily-user-engagement {
        position: relative;
        width: calc(100% + 40px) !important;
        margin-left: -20px;

        > div {
            position: relative;
            z-index: 2;
        }

        .line {
            position: absolute;
            width: calc(100% - 40px);
            height: 1px;
            background-color: #e8e8e8;
            left: 50%;
            transform: translateX(-50%);
            top: 0;
            z-index: 1;

            &-1 {
                top: 0%;
            }

            &-2 {
                top: 25%;
            }

            &-3 {
                top: 50%;
            }
        }
    }

    .daily-user-engagement, .companies-signup {
        g[text-anchor="middle"] {
            background-color: red;

            g:first-child {
                text-anchor: start;
            }

            g:last-child {
                text-anchor: end;
            }
        }
    }

    .card {
        .card-title {
            color: #b3c1cb;
            font-family: "Roboto", sans-serif;
            font-size: 18px;
            letter-spacing: .3px;
            font-weight: 400;
            display: flex;
            justify-content: space-between;

            .ascendant {
                font-family: "Roboto", sans-serif;
                font-size: 25px;
                font-weight: 900;
            }
        }

        span {
            &::before {
                font-weight: 900;
                font-family: "Font Awesome 5 Free";
            }

            &.ascendant {
                color: var(--secondary-color);

                &::before {
                    content: "\f30c";
                }
            }

            &.descendant {
                color: $error-color;

                &::before {
                    content: "\f309";
                }
            }
        }

        table {
            font-family: "Opens sans", sans-serif;

            tr {
                td {
                    border-top: 0;
                    border-bottom: 1px solid #dee2e6;
                    padding: .5rem;

                    .td-title {
                        font-weight: 700;
                        color: #4d4f5c;
                        font-size: 16px;
                    }

                    span {
                        font-size: 16px;
                        margin-left: 10px;
                        color: #707070;
                        letter-spacing: .3px;
                    }

                    &:last-child {
                        text-align: right;
                    }
                }
            }
        }
    }
}
</style>
