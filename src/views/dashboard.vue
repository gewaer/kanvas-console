<template>
    <div class="dashboard">
        <h4 class="section-title p-l-10">
            Dashboard
        </h4>
        <div class="row align-items-center mb-5">
            <div class="col-3">
                <h1 class="title mb-0">
                    Project Overview
                </h1>
            </div>
            <div class="col">
                <div class="row">
                    <div class="col">
                        <div :class="allAppsConected ? 'all-apps-onnected' : 'reconnect-apps'" class="apps-status h-100">
                            <span>{{ allAppsConected ? 'All Apps connected' : 'Reconnect Apps' }}</span>
                            <i class="fas" />
                        </div>
                    </div>
                    <div class="col">
                        <div class="get-your-keys card h-100">
                            <span>Get your Keys</span>
                            <i class="fas fa-key" />
                        </div>
                    </div>
                    <div class="col">
                        <div class="download-sdk">
                            <div class="row mb-3">
                                <div class="col">
                                    <span class="download-sdk-title">Download SDK</span>
                                </div>
                                <div class="col-auto text-right">
                                    <a class="get-other-downloads d-flex align-items-center" href="#">
                                        Get other downloads
                                        <i class="ml-2 fas fa-download" />
                                    </a>
                                </div>
                            </div>
                            <div class="row download-sdk-links">
                                <div class="col">
                                    <button class="btn">Web</button>
                                </div>
                                <div class="col">
                                    <button class="btn">Mobile</button>
                                </div>
                                <div class="col">
                                    <button class="btn">CLI</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mb-4">
            <div class="d-flex align-items-center col">
                <span class="mr-3">Filters</span>
                <multiselect
                    :options="['Option 1', 'Option 2']"
                    :multiple="true"
                    :show-labels="false"
                />
            </div>
            <div class="col-auto">
                <button
                    class="btn btn-primary"
                >
                    Add apps
                    <i class="ml-2 fas fa-link" />
                </button>
            </div>
            <div class="col-auto">
                <button
                    class="btn btn-primary"
                >
                    Browse companies
                    <i class="ml-2 fas fa-building" />
                </button>
            </div>
            <div class="d-flex align-items-center col-auto">
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
            <div class="col-4">
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
            <div class="col-8">
                <la-cartesian autoresize :bound="[0, 25000]" :data="companiesSignups">
                    <defs>
                        <linearGradient id="area-fill" x1="0" y1="0" x2="0" y2="1" />
                    </defs>
                    <la-area fill-color="url(#area-fill)" color="red" curve animated prop="value" />
                    <la-x-axis :font-size="12" prop="name" :interval="30" gridline :gridlineInterval="5" />
                    <la-y-axis :font-size="12" :format="(value) => `$${value/1000}k`" :ticks="[5000, 10000, 15000, 20000, 25000]" gridline :gridlineInterval="5" />
                </la-cartesian>
            </div>
        </div>
        <div class="row section">
            <div class="col">
                <div class="card padding-20">
                    <div class="card-title">
                        Test 1
                    </div>
                    <div class="card-body">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                    </div>
                </div>
            </div>
            <div class="col">
                <div class="card padding-20">
                    <div class="card-title">
                        Test 2
                    </div>
                    <div class="card-body">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                    </div>
                </div>
            </div>
            <div class="col">
                <div class="card padding-20">
                    <div class="card-title">
                        Test 3
                    </div>
                    <div class="card-body">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                    </div>
                </div>
            </div>
        </div>
        <div class="row section">
            <div class="col">
                <div class="card padding-20">
                    <div class="card-title">
                        Test 4
                    </div>
                    <div class="card-body">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                    </div>
                </div>
            </div>
            <div class="col">
                <div class="card padding-20">
                    <div class="card-title">
                        Test 5
                    </div>
                    <div class="card-body">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { Cartesian, Area, XAxis, YAxis } from "laue";

export default {
    name: "Home",
    components: {
        LaCartesian: Cartesian,
        LaArea: Area,
        LaXAxis: XAxis,
        LaYAxis: YAxis
    },
    data() {
        return {
            dropdown: "Last 6 Months",
            allAppsConected: true,
            companiesSignups: [
                { name: "Nov 10, 2017", value: 5500 },
                { name: "Nov 11, 2017", value: 13500 },
                { name: "Nov 12, 2017", value: 11500 },
                { name: "Nov 13, 2017", value: 15100 },
                { name: "Nov 14, 2017", value: 9500 },
                { name: "Nov 15, 2017", value: 14500 },
                { name: "Nov 16, 2017", value: 12500 },
                { name: "Nov 17, 2017", value: 15500 },
                { name: "Nov 18, 2017", value: 10500 },
                { name: "Nov 19, 2017", value: 13500 },
                { name: "Nov 20, 2017", value: 10000 },
                { name: "Nov 21, 2017", value: 15000 },
                { name: "Nov 22, 2017", value: 10000 },
                { name: "Nov 23, 2017", value: 13000 },
                { name: "Nov 24, 2017", value: 10000 },
                { name: "Nov 25, 2017", value: 12500 },
                { name: "Nov 26, 2017", value: 5000 },
                { name: "Nov 27, 2017", value: 10000 },
                { name: "Nov 28, 2017", value: 9500 },
                { name: "Nov 29, 2017", value: 11000 },
                { name: "Nov 30, 2017", value: 14000 },
                { name: "Dic 01, 2017", value: 10000 },
                { name: "Dic 02, 2017", value: 9000 },
                { name: "Dic 03, 2017", value: 13000 },
                { name: "Dic 04, 2017", value: 17000 },
                { name: "Dic 05, 2017", value: 12000 },
                { name: "Dic 06, 2017", value: 10000 },
                { name: "Dic 07, 2017", value: 6000 },
                { name: "Dic 08, 2017", value: 10000 },
                { name: "Dic 09, 2017", value: 14000 },
                { name: "Dic 10, 2017", value: 12000 }
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

    .card {
        .card-title {
            color: #b3c1cb;
            font-family: "Opens sans", sans-serif;
            font-size: 18px;
            letter-spacing: .5px;
            font-weight: 400;
            display: flex;
            justify-content: space-between;

            .ascendant {
                font-family: "Lato";
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
